# Modules

* [AirBNB JavaScript Style Guide: Modules](https://github.com/airbnb/javascript#modules)
  * 10.1 Always use modules \(import/export\) over a non-standard module system.
  * 10.2 Do not use wildcard imports.
  * 10.6 In modules with a single export, prefer default export over named export.
    * Interpretation: multiple exports allowed
* Confusing as hell
  * ESM vs CommonJS vs ES6

If using `export default` use `import var from module`:

```javascript
export const foo = 42
export default 21;
```

If you want the `21`, use `import bar from './input';`

```javascript
import barImport from './input';
console.log(barImport); // 21

const barRequire = require('./input');
console.log(barRequire);
/*
{
    foo: 42,
    default: 21,
}
*/
```

#### Notes

```javascript
export const types = () => {}
```

is different from

```javascript
export function types() { }
```

* [https://nodejs.org/api/modules.html](https://nodejs.org/api/modules.html)
* [http://2ality.com/2014/09/es6-modules-final.html](http://2ality.com/2014/09/es6-modules-final.html)
* [https://stackoverflow.com/questions/40294870/module-exports-vs-export-default-in-node-js-and-es6](https://stackoverflow.com/questions/40294870/module-exports-vs-export-default-in-node-js-and-es6)

#### Clearing Confusing

|  |  |  | Goals |  |
| :--- | :--- | :--- | :--- | :--- |
| CommonJs | `module.exports = ...` | `var module = require('module')` |  |  |
| AMD |  | define\(\['dependency1'\], function\(dependency1 | Load synchronously | Asynchronous Module Definition |
| UMD |  |  |  | Universal Module Definition |
| ESM |  |  |  |  |

* [https://medium.freecodecamp.org/javascript-modules-a-beginner-s-guide-783f7d7a5fcc](https://medium.freecodecamp.org/javascript-modules-a-beginner-s-guide-783f7d7a5fcc)

## 

