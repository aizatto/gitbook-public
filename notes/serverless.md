---
description: 'Notes for https://serverless.com'
---

# Serverless

## Commands

```bash
serverless create --template aws-nodejs-typescript --path project-name
```

## Best Practices / Learnings So Far

* Don't overload your `serverless.yml` with many services.
  * See DynamoDB gotcha
* Failures can leave your deployment in an uncertain state
* Rename your Amazon API Gateway
  * [https://github.com/aizatto/serverless-prototypes/tree/master/aws-apigateway-proxy](https://github.com/aizatto/serverless-prototypes/tree/master/aws-apigateway-proxy)

## AWS - Invoke Local

[https://serverless.com/framework/docs/providers/aws/cli-reference/invoke-local/](https://serverless.com/framework/docs/providers/aws/cli-reference/invoke-local/)

```bash
serverless invoke local --function functionName
```

If you want to pass a url into the `event.body`

```javascript
JSON.stringify({ body: JSON.stringify($value)})
```

Then:

```bash
serverless invoke local --function functionName --data $string
```

## API Gateway Gotchas

### API Gateway Bad Naming

By default Serverless names the API Gateway as `$stage-$service`

This is not scaleable when you have many services. To fix this update your `serverless.yml`:

```yaml
resources:
  Resources:
    ApiGatewayRestApi:
      Type: AWS::ApiGateway::RestApi
      Properties:
        Name: ${self:service}-${opt:stage}
```

## DynamoDB

### Gotchas

WARNING: Changing table names drops the original database.

Be very careful.

#### Cannot reuse existing DynamoDBs

Serverless cannot reuse existing DyanmoDB tables. It will error our if you try to use it:

> An error occurred: eventsTable - $table already exists.

[https://github.com/serverless/serverless/issues/3183](https://github.com/serverless/serverless/issues/3183)

#### Billing Mode: Pay Per Request

I ran into bugs trying to move to "PAY\_PER\_REQUEST" mode, and then I couldn't deploy, and when I think I fixed this, I got this error:

> An error occurred: $table - Subscriber limit exceeded: Update to PayPerRequest mode are limited to once in 1 day\(s\). Last update at Sat Feb 23 03:07:45 UTC 2019. Next update can be made at Sun Feb 24 03:07:45 UTC 2019 \(Service: AmazonDynamoDBv2; Status Code: 400; Error Code: LimitExceededException; Request ID: E2GS9JLCCLIUH8BNIPQN32UEDBVV4KQNSO5AEMVJF66Q9ASUAAJG\).

### Plugin: serverless-dynamodb-local

[https://www.npmjs.com/package/serverless-dynamodb-local](https://www.npmjs.com/package/serverless-dynamodb-local)

This seems like a poor plugin.

* Have to use `v0.2.30`
* Constantly has problems running
  * Have to consistently remove and install

Useful locally for:

* migrations
* seeding

Use `v0.2.30`, there are problems with the latest version.

```bash
yarn add --dev serverless-dynamodb-local@0.2.30
```

## Roles

By default, the roles you create apply to all functions.

You can define individual roles to functions via [https://github.com/functionalone/serverless-iam-roles-per-function](https://github.com/functionalone/serverless-iam-roles-per-function)

## Serverless Alternatives

* [https://up.docs.apex.sh/](https://up.docs.apex.sh/)
* [https://zeit.co/](https://zeit.co/)
* [https://github.com/awslabs/serverless-application-model](https://github.com/awslabs/serverless-application-model)
* [https://www.netlify.com/docs/functions/](https://www.netlify.com/docs/functions/)
* [https://workers.dev/](https://workers.dev/)
* [http://fnproject.io/](http://fnproject.io/)

### AWS Serverless Application Model \(SAM\)

Pros:

* Directly define CloudFormation naming

Cons:

* More complex flags to use for deploying
* No templating

## Personal Prototypes / Toys / Experiments

* [URL Shortener](https://github.com/aizatto/url-shortener/)



