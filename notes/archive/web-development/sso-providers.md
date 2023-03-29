---
description: SSO (Single Sign On) Providers
---

# SSO Providers

## Providers

* Auth0
  * [https://auth0.com/](https://auth0.com/)
* AWS Cognito
  * [http://aws.amazon.com/cognito](http://aws.amazon.com/cognito)

Pros:

* Have someone manage your user accounts for you
  * \(Security, balancing, availability\)
* They take care of the CRUD

### Auth0

* Prettier interface
* Better documentation

Options

* [https://auth0.com/docs/quickstart/webapp/nodejs](https://auth0.com/docs/quickstart/webapp/nodejs)
* [https://auth0.com/docs/quickstart/backend/hapi/01-authorization](https://auth0.com/docs/quickstart/backend/hapi/01-authorization)

### AWS Cognito

* Cheaper
* "Drier" / Bleak interface
* Confusing as hell
* You can give individual users IAM roles
* Can be configured with serverless
  * But not all configuration options

Cons:

* You may only be able to log in to one SSO at a time.
  * This is bad if you want to attache one user account to multiple providers

