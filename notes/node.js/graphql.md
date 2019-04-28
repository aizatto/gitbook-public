---
description: This page refers to the GraphQL JavaScript package
---

# GraphQL

* [http://github.com/graphql/graphql](https://github.com/graphql/graphql-js)
* [https://www.aizatto.com/notes/graphql](https://www.aizatto.com/notes/graphql)

## Directory Structure

```text
src/graphql/Schema.ts
src/graphql/Mutation.ts
src/graphql/User.ts (GraphQLObjectType)
src/graphql/mutations/UserMutation.ts
```

## Schema

Put edges in a "Viewer" GraphQLObjectType so that you can use it as the "root" object.

```graphql
type Query {
  entries(order: String, sort: String, after: String, first: Int, before: String, last: Int): EntryConnection
  tags(after: String, first: Int, before: String, last: Int): TagConnection
  viewer: Viewer
}

type Viewer implements EntryConnectionInterface {
  entries(order: String, sort: String, after: String, first: Int, before: String, last: Int): EntryConnection
  tags(after: String, first: Int, before: String, last: Int): TagConnection
}
```

