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

