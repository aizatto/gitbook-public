---
description: 'Notes for https://serverless.com'
---

# Serverless

## Commands

```bash
serverless create --template aws-nodejs-typescript --path project-name
```

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

## serverless-dynamodb-local

[https://www.npmjs.com/package/serverless-dynamodb-local](https://www.npmjs.com/package/serverless-dynamodb-local)

This seems like a poor plugin.

* Have to use `v0.2.30`
* Constantly has problems running

Useful locally for:

* migrations
* seeding

Use `v0.2.30`, there are problems with the latest version.

```bash
yarn add --dev serverless-dynamodb-local@0.2.30
```

## Serverless Alternatives

* [https://up.docs.apex.sh/](https://up.docs.apex.sh/)
* [https://zeit.co/](https://zeit.co/)

## Personal Prototypes / Toys / Experiments

* [URL Shortener](https://github.com/aizatto/url-shortener/)

WARNING: Changing table names drops the original database.

Be very careful.

