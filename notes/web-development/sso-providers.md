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

### AWS Cognito

* Cheaper
* "Drier" / Bleak interface
* Confusing as hell
* You can give individual users IAM roles

Cons:

* You may only be able to log in to one SSO at a time.
  * This is bad if you want to attache one user account to multiple providers

