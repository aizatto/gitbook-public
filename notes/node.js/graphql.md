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

## Resolvers

Naming:

* Postfix function names with `Resolver`
* Pass in all the args: `root, args, context, info`

{% code title="Entry.ts" %}
```typescript
// For the connections
`query {
  entries(...) {
     edges...
  }
}`
export async function EntriesResolver(root, args, context, info);

`query {
  entry(...) { }
}`
export async function EntryResolver(root, args, context, info);

// My suggestion is put this function in the `Tag.ts` file.
// The goal is put all Resolvers that query the same database in the same file
`query {
  entry(...) {
    tags(...) { 
      edges...
    }
  }
}`
export async function EntryTagsResolver(root, args, context, info) {
  const row = await knex
    .from("tags")
    .where({
      tag.entryID: root.id,
    })
    .select();
    
  ...
}
```
{% endcode %}

```typescript
export async function EntryResolver(
  root,
  args,
  context: Context,
  info
): Promise<any> {
  const userUUID = getUserUUIDFromContext(context);

  const where = {
    uuid: args.uuid,
    createdBy: userUUID
  };

  const row = await knex
    .from("users")
    .where(where)
    .limit(1)
    .select();
  return row.shift();
}
```

## Bugs

## Could not convert from GraphQL type String

When running `relay-compiler` I would get this error:

> Could not convert from GraphQL type String

Environment: Lerna with multiple `graphql` packages installed

Solution specify `resolutions` in local `package.json`:

{% code title="package.json" %}
```text
"resolutions": {
  "graphql": $your_version
}
```
{% endcode %}

Worse case, nuke your `node_modules`:

```bash
rm -rf \
  packages/your-package/node_modules/ \
  node_modules/ \
  yarn.lock
```

