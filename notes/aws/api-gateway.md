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

Originally from [http://www.leanx.eu/tutorials/set-up-amazons-api-gateway-custom-domain-with-cloudflare](http://www.leanx.eu/tutorials/set-up-amazons-api-gateway-custom-domain-with-cloudflare)

Recreating here.

1. Open [Cloudflare](https://dash.cloudflare.com/)
   1. Select your domain and open the "Crypto" tab
   2. Go to "Origin Certificates" and click "Create Certificate"
   3. Let Cloudflare generate a private key and a CSR and choose RSA as the private key type
   4. Make sure that the hostname for your custom API domain is covered. E.g. api.mydomain.com. You can specifically configure this custom domain or use a wildcard such as \*.mydomain.com as is configured by default.
   5. Select `PEM` as the `Key format`
2. Open [AWS ACM Console](https://console.aws.amazon.com/acm/home)
   1. Click "Import Certificate"
   2. Copy from Cloudflare "`Origin Certificate`" to AWS ACM "`Certificate body`"
   3. Copy from Cloudflare "`Private key`" to AWS "`Certificate private key`"
   4. In the certificate chain copy the "`Cloudflare Origin CA - RSA Root`" which can be found here: [https://support.cloudflare.com/hc/en-us/articles/115000479507](https://support.cloudflare.com/hc/en-us/articles/115000479507)
   5. Click "Review and Import"
3. Open [AWS API Gateway](https://console.aws.amazon.com/apigateway/home#/custom-domain-names)
   1. Select "[Custom Domain Names](https://console.aws.amazon.com/apigateway/home#/custom-domain-names)" from the left menu.
   2. Click the "Create Custom Domain Name" button.
   3. The next thing you need to do is set up the Mappings of the custom domain in the AWS Console.
4. In Cloudflare, open the "DNS" tab
   1. The final step is to create a new CNAME record in CloudFlare to link your domain to the Cloudfront url. When you open the settings page of your custom domain in the AWS console copy the Distribution domain name. This is the domain you need to use when creating the new CNAME record.

