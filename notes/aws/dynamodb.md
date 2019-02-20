# DynamoDB

* [Best Practices](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html)

## Node.js

To store Timestamp:

```javascript
new Date().toISOString()
```

## Gotchas

### Serverless

WARNING: Changing the table name in `serverless.yml` will drop the table.

### DynamoDB Shell

* [http://localhost:8000/shell](http://localhost:8000/shell)
* Works better in Chrome vs Safari

### [Reserved Words](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ReservedWords.html)

* `counter`
* `name`
* `source`
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

`GetItem` cannot be preformed on a `Global Secondary Index`.

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

### Query vs Scan

[https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API\_Query.html](https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_Query.html)  
[https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API\_Scan.html](https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_Scan.html)

| Query | Scan |
| :--- | :--- |
| The Query operation finds items based on primary key values. You can query any table or secondary index that has a composite primary key \(a partition key and a sort key\). | The `Scan` operation returns one or more items and item attributes by accessing every item in a table or a secondary index. To have DynamoDB return fewer items, you can provide a `FilterExpression` operation.  |

## Indexes

[https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-indexes-general.html](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-indexes-general.html)

[https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SecondaryIndexes.html](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SecondaryIndexes.html)

| Global Secondary Index | Local Secondary Index |
| :--- | :--- |
| An index with a partition key and a sort key that can be different from those on the base table. | An index that has the same partition key as the base table, but a different sort key. |
| A global secondary index has no size limitations and has its own provisioned throughput settings for read and write activity that are separate from those of the table. | As a result, the total size of indexed items for any one partition key value can't exceed 10 GB. Also, a local secondary index shares provisioned throughput settings for read and write activity with the table it is indexing. |
| Each table in DynamoDB is limited to 20 global secondary indexes \(default limit\) | Each table in DynamoDB is limited to 5 local secondary indexes. |

### Global Secondary Index

Cannot perform `GetItem`. Use `Query` or `Scan`.  
[https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-indexes-general.html](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-indexes-general.html)

