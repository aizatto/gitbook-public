# API Gateway

## Common Errors

### Works in Lambda, but not in API Gateway

Testing in API Gateway:

Status: 502

Response Body:

```javascript
{
  "message": "Internal server error"
}
```

Logs:

> Lambda execution failed with status 200 due to customer function error: RequestId: 80572150-944e-40e5-b782-aca7f713289f Process exited before completing request. Lambda request id: 80572150-944e-40e5-b782-aca7f713289f

#### Solution

Check your lambda function is either:

* Make sure you define your handler function `async` ; or
* Use the `callback` argument in your handler

For example:

```typescript
export async function webhook(event, context) {
  return {
    statusCode: 200,
  };
}
```

or

```typescript
export function webhook(event, context, callback) {
  callback(null, { statusCode: 200 });
}
```

## Using Custom Domains with Cloudflare

1. Open [Cloudflare](https://dash.cloudflare.com/)
   1. Select your domain and open the "Crypto" tab
   2. Change "SSL" to "Full \(strict\)"
   3. Go to "Origin Certificates" and click "Create Certificate"
   4. Generate a private key and a CSR and choose RSA as the private key type
   5. Make sure that the hostname for your custom API domain is covered. E.g. api.mydomain.com. You can specifically configure this custom domain or use a wildcard such as \*.mydomain.com as is configured by default.
   6. Select `PEM` as the `Key format`
2. Open [AWS ACM Console](https://console.aws.amazon.com/acm/home) \(us-east-1\)
   1. Click "Import Certificate"
   2. Copy from Cloudflare "`Origin Certificate`" to AWS ACM "`Certificate body`"
   3. Copy from Cloudflare "`Private key`" to AWS "`Certificate private key`"
   4. In the certificate chain copy the "`Cloudflare Origin CA - RSA Root`" which can be found here: [https://support.cloudflare.com/hc/en-us/articles/115000479507\#h\_30cc332c-8f6e-42d8-9c59-6c1f06650639](https://support.cloudflare.com/hc/en-us/articles/115000479507#h_30cc332c-8f6e-42d8-9c59-6c1f06650639)
   5. Click "Review and Import"
3. Open [AWS API Gateway](https://console.aws.amazon.com/apigateway/home#/custom-domain-names)
   1. Select "[Custom Domain Names](https://console.aws.amazon.com/apigateway/home#/custom-domain-names)" from the left menu.
   2. Click the "Create Custom Domain Name" button.
   3. Enter the "Domain Name"
   4. Select the ACM Certificate \(us-east-1\)
   5. Click "Base Path Mappings"
      1. Set the relevant path and destination
   6. Hit "Save"
   7. Wait a maximum of 40 minutes
4. In Cloudflare, open the "DNS" tab
   1. Add a CNAME record
      1. For "Name":
         1. Use "@" if you are targeting the root domain. For example "build.my"
         2. Use "www" if you are targetting a subdomain. For example: "www.build.my"
      2. For "Domain name":
         1. Use the AWS APIGateway Target Domain Name. For example: "d1jdvkqtea2e81.cloudfront.net"
      3. For Status:
         1. Set to: Traffic to this hostname will go through Cloudflare / DNS and HTTP Proxy \(CDN\)

Test only on `https` . Testing on `http` will redirect to `https` so it looks like nothing is happening.

```bash
curl --verbose https://dt.cards/
```

Pieced from:

* [https://stackoverflow.com/questions/36737313/how-to-cname-to-amazon-api-gateway-endpoint](https://stackoverflow.com/questions/36737313/how-to-cname-to-amazon-api-gateway-endpoint)
* [http://www.leanx.eu/tutorials/set-up-amazons-api-gateway-custom-domain-with-cloudflare](http://www.leanx.eu/tutorials/set-up-amazons-api-gateway-custom-domain-with-cloudflare)
* [https://medium.com/@bobthomas295/combining-aws-serverless-with-cloudflare-sub-domains-338a1b7b2bd](https://medium.com/@bobthomas295/combining-aws-serverless-with-cloudflare-sub-domains-338a1b7b2bd)



