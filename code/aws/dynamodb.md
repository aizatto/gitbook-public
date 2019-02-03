# DynamoDB

* * [Best Practices](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html)

## Gotchas

### DynamoDB Shell

* [http://localhost:8000/shell](http://localhost:8000/shell)
* Works better in Chrome vs Safari

### [Reserved Words](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ReservedWords.html)

* `counter`
* `name`
* `url`
* `uuid`
* `value`

### Promises \(async/await\)

```javascript
const { promisify } = require('util');
...
dynamodb.putPromise = promisify(dynamodb.put);
dynamodb.updatePromise = promisify(dynamodb.update);
dynamodb.getPromise = promisify(dynamodb.get);
...
result = await dynamodb.putPromise({});
result = await dynamodb.updatePromise({});
result = await dynamodb.getPromise({});

```

### [GetItem](https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_GetItem.html)

```javascript
// Does not throw an exception if record does not exist
const result = await dynamodb.getPromise({});

if (!result.Item) {
  // exit early
}
```

### [PutItem](https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_PutItem.html)

Will overwrite values if the key is the same; unless you define a ConditionalExpression

> If an item that has the same primary key as the new item already exists in the specified table, the new item completely replaces the existing item. You can perform a conditional put operation \(add a new item if one with the specified primary key doesn't exist\), or replace an existing item if it has certain attribute values. You can return the item's attribute values in the same operation, using the `ReturnValues`parameter.

#### [ConditionalExpression](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.ConditionExpressions.html)

```javascript
docClient.put(
  {
    TableName: 'Example',
    Item: {
      CounterName: 'Example1',
    },
    ConditionExpression: 'attribute_not_exists(CounterName)'
  },
  function (error, data) {
    if (error) {
      // If conflict, an error will be thrown
    } else {
      
    }
  }
);
```

When using `ConditionExpression`, and if there is a conflicting.

Sample error:

```javascript
{
    "message":"The conditional request failed",
    "code":"ConditionalCheckFailedException",
    "time":"2019-02-03T09:20:20.260Z",
    "statusCode":400,
    "retryable":false
}
```

