# AWS



* [AWS Console](https://console.aws.amazon.com/console/home)
* [AWS Calculator](https://calculator.s3.amazonaws.com/index.html)
* [Mapping of AWS to GCP](https://cloud.google.com/free/docs/map-aws-google-cloud-platform)

| Service | Features | Pricing | Getting Started | Resources | Limits |
| :--- | :--- | :--- | :--- | :--- | :--- |
| [API Gateway](https://aws.amazon.com/api-gateway/) |  | [Pricing](https://aws.amazon.com/api-gateway/pricing/) |  |  |  |
| Cognito | [Features](https://aws.amazon.com/cognito/details/) | [Pricing](https://aws.amazon.com/cognito/pricing/) | [Getting Started](https://aws.amazon.com/cognito/getting-started/) | [Resources](https://aws.amazon.com/cognito/dev-resources/) | [Limits](https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html#limits_cognito_user_pools) |
| [CloudFormation](https://aws.amazon.com/cloudformation/) |  | [Pricing](https://aws.amazon.com/cloudformation/pricing/) |  |  |  |

Pros:

* Flexibility of AWS's IAM Permissions and Roles

Cons:

* No ability to export an application and view at a glance settings,

Comments:

* More configuring than coding

Limitations:

* Not everything lives in code

## Tips

[aws-shell](https://github.com/awslabs/aws-shell)

```bash
pip install aws-shell
```

## Services

### API Gateway

> Create, maintain, and secure APIs at any scale

[https://aws.amazon.com/api-gateway/](https://aws.amazon.com/api-gateway/)

### AppSync

[https://docs.aws.amazon.com/appsync/latest/devguide/designing-your-schema.html](https://docs.aws.amazon.com/appsync/latest/devguide/designing-your-schema.html)

Keywords:

* GraphQL
* Relay

[https://medium.com/open-graphql/using-relay-with-aws-appsync-55c89ca02066](https://medium.com/open-graphql/using-relay-with-aws-appsync-55c89ca02066) [https://github.com/aws-samples/aws-appsync-relay](https://github.com/aws-samples/aws-appsync-relay)

Pros:

* GraphQL Code Gen

Cons:

* Does not support a dyanmic GraphQL Schema
* Will expose all of a GraphQL Schema
* Point and click engineering

Questions:

* Can AppSync return currently logged in user?
* How do you do test/dev/staging environments?
* How do I export an AppSync?
* How to elastic search?
* How many LOC is an average schema?

Limitations:

* Not everything lives in code
* Doesn't look like it can handle complex GraphQL Schemas
* AppSync's GraphQL Schema uses its own private directive
* Won't scale to lots of types

[https://medium.com/@dadc/aws-appsync-the-unexpected-a430ff7180a3](https://medium.com/@dadc/aws-appsync-the-unexpected-a430ff7180a3)

* Responses have to take less than 10secs
* Maximum array sizes is 1000
* Responses have to be less than 1MB
* Cannot compress response

### With DynamoDB

> If you're doing the advanced section with pagination and relations, you need to repeat the above with a table named Comments with a primary key of todoid and a sort key of commentid, where both are of type String. Additionally, you must create a global secondary index on the table called todoid-index with a partition key todoid of type String. You can create this manually in the Amazon DynamoDB console or using the following AWS CloudFormation stack:

### Amplify

[https://aws-amplify.github.io/docs/js/api](https://aws-amplify.github.io/docs/js/api)

> The foundation for your cloud-powered mobile & web apps

### CloudFormation

> Model and provision all your cloud infrastructure resources

[http://aws.amazon.com/cloudformation/](http://aws.amazon.com/cloudformation/)

### Cognito

[https://aws.amazon.com/cognito/](https://aws.amazon.com/cognito/)

[https://aws.amazon.com/cognito/pricing/](https://aws.amazon.com/cognito/pricing/)

> Amazon Cognito lets you add user sign-up, sign-in, and access control to your web and mobile apps quickly and easily.

Competitors:

* Auth0

Pricing:

* [cognito](https://aws.amazon.com/cognito/pricing/)
* [auth0](https://auth0.com/pricing)

> Users who sign in directly with their User Pool credentials or with social identity providers:

| Pricing Tier \(MAUs\) | Price Per MAU | Total Users |  |
| :--- | ---: | ---: | ---: |
| First 50,000 | Free | 50,000 | $0 |
| Next 50,000 | $0.00550 | 100,000 | $275 |
| Next 900,000 | $0.00460 | 950,000 | $4,140 |
| Next 9,000,000 | $0.00325 | 9,950,000 | $29,250 |
| Greater than 10,000,000 | $0.00250 |  |  |

Cons:

* Message customization won't allow experimentation

Concerns:

* How to handle internationalization?
  * Use custom lambda triggers

Only supports:

* Amazon
* Facebook
* Google

### DynamoDB

> Amazon DynamoDB is a nonrelational database that delivers reliable performance at any scale.

* [Pricing](https://aws.amazon.com/dynamodb/pricing/)
* NoSQL Database
* Partition Key, Sort Key

### Search / Filter

### Sort

### Fargate

> Run containers without managing servers or clusters

### IAM \(Identity and Access Management\)

### Lambda

> Run code without thinking about servers. Pay only for the compute time you consume.

### Pinpoint

> Engage your customers by sending them targeted and transactional email, SMS, push notifications, and voice messages.

### Redshift

> Amazon Redshift is a fast, scalable data warehouse that makes it simple and cost-effective to analyze all your data across your data warehouse and data lake.

### SES \(Simple Email Service\)

> Flexible, affordable, and highly-scalable email sending and receiving platform for businesses and developers

### Simple Notification Service

> Fully managed pub/sub messaging for microservices, distributed systems, and serverless applications

[https://stackoverflow.com/questions/13681213/what-is-the-difference-between-amazon-sns-and-amazon-sqs](https://stackoverflow.com/questions/13681213/what-is-the-difference-between-amazon-sns-and-amazon-sqs)

### Simple Queue System

> Fully managed message queues for microservices, distributed systems, and serverless applications

[https://aws.amazon.com/sqs/](https://aws.amazon.com/sqs/)

## Glossary

[https://docs.aws.amazon.com/general/latest/gr/glos-chap.html](https://docs.aws.amazon.com/general/latest/gr/glos-chap.html)

| Term | Definition |
| :--- | :--- |
| ARN | Amazon Resource Name |
| IAM | Identity and Access Management |

