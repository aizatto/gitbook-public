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
npx lerna bootstrap --npm-client=yarn --use-workspaces
```

Update `lerna.json`

{% code title="lerna.json" %}
```javascript
{
  "npmClient": "yarn",
  "useWorkspaces": "true"
}
```
{% endcode %}

Install

```bash
yarn install
```

Update `package.json`

{% code title="package.json" %}
```javascript
{
  "scripts": {
    "lint": "yarn run lerna run lint"
  },
  "workspaces": ["packages/*"]
}
```
{% endcode %}

`package.json` when creating a new package:

{% code title="packages/new-package/package.json" %}
```javascript
{
  "name": "new-package",
  "private": true,
  "version": "0.0.0"
}
```
{% endcode %}

#### Package Management

Each package manages it's own `typescript` and `eslint`.

For example, at the root directory.

```bash
yarn lerna run lint
```

## Use JSON5 over JSON

> The JSON5 Data Interchange Format \(JSON5\) is a superset of [JSON](https://tools.ietf.org/html/rfc7159) that aims to alleviate some of the limitations of JSON by expanding its syntax to include some productions from [ECMAScript 5.1](https://www.ecma-international.org/ecma-262/5.1/).

* [https://json5.org/](https://json5.org/)
* [https://github.com/json5/json5](https://github.com/json5/json5)
* [https://www.npmjs.com/package/json5](https://www.npmjs.com/package/json5)

```bash
yarn add json5
```

JSON5 Short Example:

```javascript
{
  // comments
  unquoted: 'and you can quote me on that',
  singleQuotes: 'I can use "double quotes" here',
  lineBreaks: "Look, Mom! \
No \\n's!",
  newLine: "1\n\
2\n\
3",
  hexadecimal: 0xdecaf,
  leadingDecimalPoint: .8675309, andTrailing: 8675309.,
  positiveSign: +1,
  trailingComma: 'in objects', andIn: ['arrays',],
  "backwardsCompatible": "with JSON",
}
```

## Package Recommendations

### commander: command-line arguments

* [https://www.npmjs.com/package/commander](https://www.npmjs.com/package/commander)
* Used by `create-react-app`

```bash
yarn add commander
```

### dotenv

* [https://github.com/motdotla/dotenv](https://github.com/motdotla/dotenv)
* Used by `create-react-app`

```bash
yarn add dotenv
```

As early as possible:

JavaScript:

```javascript
require('dotenv').config()
```

TypeScript:

```typescript
import { config: dotenv } from "dotenv"
dotenv();
```

### fs-extra

> `fs-extra` adds file system methods that aren't included in the native `fs` module and adds promise support to the `fs` methods. It also uses [`graceful-fs`](https://github.com/isaacs/node-graceful-fs) to prevent `EMFILE`errors. It should be a drop in replacement for `fs`.

* [https://www.npmjs.com/package/fs-extra](https://www.npmjs.com/package/fs-extra)
* Used by `create-react-app`

```bash
yarn add fs-extra
```

