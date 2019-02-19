---
description: 'Notes for https://serverless.com'
---

# Serverless

## Gotchas

### DynamoDB

WARNING: Changing table names drops the original database.

Be very careful.

Use `v0.2.30`, there are problems with the latest version.

```bash
yarn add --dev serverless-dynamodb-local@0.2.30
```

