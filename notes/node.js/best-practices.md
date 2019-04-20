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

Install

```bash
yarn install
```

Update `package.json`

{% code-tabs %}
{% code-tabs-item title="package.json" %}
```javascript
{
  "scripts": {
    "lint": "yarn run lerna run lint"
  },
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

## Package Recommendations

### commander: command-line arguments

* [https://www.npmjs.com/package/commander](https://www.npmjs.com/package/commander)
* Used by `create-react-app`

```bash
yarn add commander
```

### fs-extras

> `fs-extra` adds file system methods that aren't included in the native `fs` module and adds promise support to the `fs` methods. It also uses [`graceful-fs`](https://github.com/isaacs/node-graceful-fs) to prevent `EMFILE`errors. It should be a drop in replacement for `fs`.

* [https://www.npmjs.com/package/fs-extra](https://www.npmjs.com/package/fs-extra)
* Used by `create-react-app`

```bash
yarn add fs-extra
```

