# Best Practices

## When starting a new project

* Use [Lerna](https://github.com/lerna/lerna)
* Use typescript
* Use eslint
* Use prettier
* Use jest
* Use husky
  * Used to lint files

See [https://github.com/aizatto/javascript-repository-template/blob/master/repositories.json](https://github.com/aizatto/javascript-repository-template/blob/master/repositories.json)

### Lerna

[https://github.com/lerna/lerna](https://github.com/lerna/lerna)

```bash
npx lerna init
```

Update `lerna.json`

{% code-tabs %}
{% code-tabs-item title="lerna.json" %}
```javascript
{
  "npmClient": "yarn",
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

### Package Management

Each package manages it's own `typescript` and `eslint`.

For example, at the root directory.

```bash
yarn lerna run lint
```

