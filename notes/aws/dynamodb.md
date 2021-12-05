# DynamoDB

* [Best Practices](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html)
* [https://aws.amazon.com/dynamodb/getting-started/](https://aws.amazon.com/dynamodb/getting-started/)
* [https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-general-nosql-design.html](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-general-nosql-design.html)

## Pricing

### Reads

1 Read Request Unit: Maximum of 4KB

| Read Type                  | Units    |
| -------------------------- | -------- |
| Strongly Consistent        | 1 Unit   |
| Eventually Consistent Read | 1/2 Unit |
| Transactional Read         | 2 Units  |

### Writes

1 Write Request Unit: Maximum of 1KB

| Write Type             | Units   |
| ---------------------- | ------- |
| Standard Write Request | 1 Unit  |
| Transactional Write    | 2 Units |

## Node.js

To store Timestamp:

```javascript
new Date().toISOString()
```

## Designing Your Tables

* Unlike traditional RDBMs, DynamoDB groups sorts by partitions.
  * Each partition returns sorted result.
* Fields used for partition keys are immutable.
  * You cannot change the values for fields which make up the partition key
  * Bad idea to use `name` as the partition key, because you won't be able to change the name of an object.

## Gotchas

### Naming

For all things naming regarding `DynamoDB`.

* DynamoDB doesn't allow you to rename tables
* DynamoDB has Reserved Words, so you'll need to use ExpressionAttributeNames to work around them.
* Table names should be prefixed when deploying. Suggested `$service-$stage-$table,` for example `build-my-prod-events`
* Index names don’t need to be prefixed.
* Index names can be reused across tables.For example:
  1. Table Events, indexname: updated at
  2. Table organizations, indexname: updated at

### vs RDBMS

DyanmoDB cannot do large "UPDATE queries", for example you cannot do:

```sql
UPDATE events
SET status = "past"
WHERE status = "upcoming" AND end_time < NOW();
```

You have to query each individual event. In this scenario, potentially look at storing the `status` as a Global Secondary Index. For example:

```javascript
const response = await dynamodb.queryPromise({
  TableName: process.env.EVENTS_TABLE,
  IndexName: process.env.EVENTS_STATUS_INDEX,
  KeyConditionExpression: "#s = :status AND #e <= :end_time",
  ExpressionAttributeNames:{
    "#s": "status",
    "#e": "end_time", 
  },
  ExpressionAttributeValues: {
    ":status": "upcoming",
    ":end_time": new Date().toISOString(),
  },
  ProjectionExpression: "id",
});

// We can use either a single BatchWriteItem or multiple UpdateItems
const promises = response.Items.map((event) =>
  dynamodb.updatePromise({
    TableName: process.env.EVENTS_TABLE,
    Key: {
      id: event.id,
    },
    UpdateExpression: "SET #s = :status",
    ExpressionAttributeNames:{
      "#s": "status",
    },
    ExpressionAttributeValues: {
      ":status": "upcoming",
    },
  })
);

await Promise.all(promises);
```

### Serverless

WARNING: Changing the table name in `serverless.yml` will drop the table.

### DynamoDB Shell

* [http://localhost:8000/shell](http://localhost:8000/shell)
* Works better in Chrome vs Safari

### [Reserved Words](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ReservedWords.html)

Work around is to use `ExpressionAttributeNames` and `ExpressionAttributeValues`

Example of using the keys:

```javascript
dynamodb.query({
  TableName: process.env.EVENTS_TABLE,
  IndexName: process.env.EVENTS_STATUS_INDEX,
  KeyConditionExpression: "#s = :status AND #e <= :end_time",
  ExpressionAttributeNames:{
    "#s": "status",
    "#e": "end_time",
  },
  ExpressionAttributeValues: {
    ":status": "upcoming",
    ":end_time": new Date().toISOString(),
  },
  ProjectionExpression: "id",
});
```

Examples of Reserved Words:

* `counter`
* `name`
* `source`
* `url`
* `uuid`
* `value`

### Promises (async/await)

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

### [GetItem](https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API\_GetItem.html)

```javascript
// Does not throw an exception if record does not exist
const result = await dynamodb.getPromise({});

if (!result.Item) {
  // exit early
}
```

`GetItem` cannot be preformed on a `Global Secondary Index`. You can't use `IndexName`.

### [PutItem](https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API\_PutItem.html)

Will overwrite values if the key is the same; unless you define a ConditionalExpression

> &#x20;If an item that has the same primary key as the new item already exists in the specified table, the new item completely replaces the existing item. You can perform a conditional put operation (add a new item if one with the specified primary key doesn't exist), or replace an existing item if it has certain attribute values. You can return the item's attribute values in the same operation, using the `ReturnValues`parameter.

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

[https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API\_Query.html](https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API\_Query.html)\
[https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API\_Scan.html](https://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API\_Scan.html)

| Query                                                                                                                                                                      | Scan                                                                                                                                                                                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| The Query operation finds items based on primary key values. You can query any table or secondary index that has a composite primary key (a partition key and a sort key). | <p>The <code>Scan</code> operation returns one or more items and item attributes by accessing every item in a table or a secondary index. To have DynamoDB return fewer items, you can provide a <code>FilterExpression</code> operation.<br></p> |

## Indexes

Sorting is all done on the same partition.

Have to partition wisely.

[https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-indexes-general.html](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-indexes-general.html)[https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SecondaryIndexes.html](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SecondaryIndexes.html)

| Global Secondary Index                                                                                                                                                  | Local Secondary Index                                                                                                                                                                                                            |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| An index with a partition key and a sort key that can be different from those on the base table.                                                                        | An index that has the same partition key as the base table, but a different sort key.                                                                                                                                            |
| A global secondary index has no size limitations and has its own provisioned throughput settings for read and write activity that are separate from those of the table. | As a result, the total size of indexed items for any one partition key value can't exceed 10 GB. Also, a local secondary index shares provisioned throughput settings for read and write activity with the table it is indexing. |
| Each table in DynamoDB is limited to 20 global secondary indexes (default limit)                                                                                        | Each table in DynamoDB is limited to 5 local secondary indexes.                                                                                                                                                                  |

### Global Secondary Index

Cannot perform `GetItem`. Use `Query` or `Scan`.\
[https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-indexes-general.html](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-indexes-general.html)

## Reducing DynamoDB costs

* Look for batch fetch
* Look for batch writes
* Look for scans
* Look for large queries
* Check projections

## Alternatives

* [Google Cloud Firestore](https://cloud.google.com/firestore/)
* [Google Cloud Bigtable](https://cloud.google.com/bigtable/)
* [Google Cloud Datastore](https://cloud.google.com/datastore/)
* [Azure Table Storage](https://azure.microsoft.com/en-us/services/storage/tables/)
