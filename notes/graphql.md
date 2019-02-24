# GraphQL

* [Presentation](https://docs.google.com/presentation/d/1d96DiC58RuIOK-fTElhLtg6Jf7WhThu_mpzrlCfXTsk/edit#slide=id.p)
* [https://facebook.github.io/relay/docs/fragment-container.html](https://facebook.github.io/relay/docs/fragment-container.html)
* [https://facebook.github.io/relay/docs/refetch-container.html](https://facebook.github.io/relay/docs/refetch-container.html)
* [https://facebook.github.io/relay/docs/pagination-container.html](https://facebook.github.io/relay/docs/pagination-container.html)

## Cons of REST

* composition of multiple resources requires multiple network requests

## Fragment  Container

[https://facebook.github.io/relay/docs/fragment-container.html](https://facebook.github.io/relay/docs/fragment-container.html)

Cons:

* Can't change the params

## Refetch Container

[https://facebook.github.io/relay/docs/refetch-container.html](https://facebook.github.io/relay/docs/refetch-container.html)

Cons:

* First set of params/variables can't be dynamic/set

## Pagination Container

[https://facebook.github.io/relay/docs/pagination-container.html](https://facebook.github.io/relay/docs/pagination-container.html)

Cons:

* Can only change the count variable, nothing else

## Best Practices

* [http://graphql.org/learn/best-practices/](http://graphql.org/learn/best-practices/)

## Ids

[https://github.com/graphql/graphql-relay-js/blob/4fdadd3bbf3d5aaf66f1799be3e4eb010c115a4a/src/node/node.js](https://github.com/graphql/graphql-relay-js/blob/4fdadd3bbf3d5aaf66f1799be3e4eb010c115a4a/src/node/node.js)

```text
import {fromGlobalId, toGlobalId} from 'graphql-relay';
let {type, id} = fromGlobalId(globalId);
let globalID = toGlobalId(type, id);
```

## Resolve

See `GraphQLFieldResolveFn` [https://graphql.org/graphql-js/type/\#graphqlobjecttype](https://graphql.org/graphql-js/type/#graphqlobjecttype)

```javascript
resolve: async (root, args, context, info)
```

```text
type GraphQLFieldResolveFn = (
  source?: any,
  args?: {[argName: string]: any},
  context?: any,
  info?: GraphQLResolveInfo
) => any
```

## Fragments

Group fragments at top, for example:

```text
fragment Example {
  ...Fragment1
  ...Fragment2
  field1
  field2
}
```

## Examples

* [https://developer.github.com/v4/](https://developer.github.com/v4/)

## Relay

* High initial cost of setting up
* relay-compiler babel etc

## Apollo

[https://www.apollographql.com/](https://www.apollographql.com/)

* Supports TypeScript

## Others

* Apollo
* Amazon Web Services \(AWS\) AppSync

