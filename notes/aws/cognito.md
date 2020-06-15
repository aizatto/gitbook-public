# Cognito

## Pros:

* Give IAM access to other users

## Cons:

* Complicated as hell
* No option to delete users from frontend
* Naming doesn't follow Amazon naming conventions

## Questions I Need To Answer:

* How much can I customize the login page?



<table>
  <thead>
    <tr>
      <th style="text-align:left">User Pools</th>
      <th style="text-align:left">Identity Pools</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">User pools are user directories that provide sign-up and sign-in options
        for your app users.</td>
      <td style="text-align:left">Identity pools provide AWS credentials to grant your users access to other
        AWS services.</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">Identity pools are used to store end user identities. To declare a new
        identity pool, enter a unique name.</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p></p>
        <p>With an identity pool, your users can obtain temporary AWS credentials
          to access AWS services, such as Amazon S3 and DynamoDB. Identity pools
          support anonymous guest users, as well as the following identity providers
          that you can use to authenticate users for identity pools:</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p></p>
        <p>User pools provide:</p>
        <ul>
          <li>Sign-up and sign-in services.</li>
          <li>A built-in, customizable web UI to sign in users.</li>
          <li>Social sign-in with Facebook, Google, and Login with Amazon, and through
            SAML and OIDC identity providers from your user pool.</li>
          <li>User directory management and user profiles.</li>
          <li>Security features such as multi-factor authentication (MFA), checks for
            compromised credentials, account takeover protection, and phone and email
            verification.</li>
          <li>Customized workflows and user migration through AWS Lambda triggers.</li>
        </ul>
      </td>
      <td style="text-align:left">
        <p></p>
        <ul>
          <li>Amazon Cognito user pools</li>
          <li>Social sign-in with Facebook, Google, and Login with Amazon</li>
          <li>OpenID Connect (OIDC) providers</li>
          <li>SAML identity providers</li>
          <li>Developer authenticated identities</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

* You can use identity pools and user pools separately or together.
* To save user profile information, your identity pool needs to be integrated with a user pool.
* [https://docs.aws.amazon.com/cognito/index.html](https://docs.aws.amazon.com/cognito/index.html)

## Social Identity Providers

URLs:

Login URL

[https://$domain/login?response\_type=code&client\_id=$client\_id&redirect\_uri=$redirect\_uri](https://$domain/login?response_type=code&client_id=$client_id&redirect_uri=$redirect_uri)

Valid OAuth Redirect URI

[https://$domain/oauth2/idpresponse  
](https://build-my-dev.auth.ap-southeast-1.amazoncognito.com/oauth2/idpresponse
)

