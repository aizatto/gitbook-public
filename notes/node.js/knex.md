# Knex

[https://knexjs.org/](https://knexjs.org/)

## CLI

```bash
yarn run knex migrate:make $NAME
yarn run knex migrate:latest
yarn run knex migrate:rollback
```

## Convenience Scripts

Update your `package.json`:

{% code title="package.json" %}
```javascript
{
  "scripts": {
    "latest": "yarn run knex migrate:latest",
    "rollback": "yarn run knex migrate:rollback"
  },
}
```
{% endcode %}

## Migrations

### Naming

```bash
yarn run knex migrate:make $verb_table
```

Examples:

```bash
yarn run knex migrate:make createTable_users
yarn run knex migrate:make alterTable_users_add_createdBy
```

Sticks to the knex function names `createTable` and `alterTable`

Avoid an "`init`" file.

{% hint style="warning" %}
Avoid an "init" file.

For example, do not have a: `20190424135724_init.js`

Instead just do: `20190424135724_create_entries.js`

This explains what the file does.
{% endhint %}

* Tables should be plural
* Fields should be in `camelCase`
  * Follows [JavaScript Style Guides](../javascript/style-guides.md) for local variables
  * Exception relational id, for example: `entryID`

Also see [Engineering Code &gt; Naming](../../engineering-code/naming.md#common-names)

### Promises:

{% code title="20190424104046\_createTable\_users.js" %}
```javascript
exports.up = function(knex, Promise) {
  return knex.schema
    .createTable('users', table => {
      table
        .uuid('uuid')
        .primary();
      table
        .datetime('createdAt')
        .defaultTo(knex.fn.now())
        .index();
      table
        .datetime('updatedAt')
        .defaultTo(knex.fn.now())
        .index();
      table
        .string('name')
        .collate('utf8mb4_unicode_ci')
        .defaultTo('')
        .notNullable();
      table
        .string('email')
        .collate('utf8mb4_unicode_ci')
        .unique()
        .defaultTo('')
        .notNullable();
    })
};

exports.down = function(knex, Promise) {
  return knex.schema
    .dropTable('users');
};
```
{% endcode %}

