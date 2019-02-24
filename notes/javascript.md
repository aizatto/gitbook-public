# JavaScript

* [http://stateofjs.com](http://stateofjs.com)
* [Reference: Node.js](/nodejs/)

## Resources

| Type | MDN |
| :--- | :--- |
| Array | [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) |
| Date | [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) |
| Object | [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) |
| String | [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) |
| JSON | [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON) |
| Set | [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) |
| RegExp | [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) |
| Destructuring Assignment | [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment) |
| const | [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) |
| let | [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let) |
| export | [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export) |

* [parseInt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)
* [parseFloat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)
* [runkit.com](https://runkit.com/)

### Style Guides

* [http://jscs.info](http://jscs.info)
* [http://eslint.org](http://eslint.org)
* [https://github.com/rwaldron/idiomatic.js](https://github.com/rwaldron/idiomatic.js)
* [https://contribute.jquery.org/style-guide/js/](https://contribute.jquery.org/style-guide/js/)
* [https://google.github.io/styleguide/jsguide.html](https://google.github.io/styleguide/jsguide.html)
* [https://github.com/airbnb/javascript](https://github.com/airbnb/javascript)
* [https://developer.mozilla.org/en-US/docs/Mozilla/Developer\_guide/Coding\_Style\#JavaScript\_objects](https://developer.mozilla.org/en-US/docs/Mozilla/Developer_guide/Coding_Style#JavaScript_objects)
* [http://standardjs.com/](http://standardjs.com/)

|  | Personal Opinion | Google | AirBNB | jQuery | Standard |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Semicolons | Required | [Required](https://google.github.io/styleguide/jsguide.html#formatting-semicolons-are-required) | [Required](https://github.com/airbnb/javascript#semicolons) | [Required](https://contribute.jquery.org/style-guide/js/#semicolons%20) | [Not Required](https://github.com/feross/standard#the-rules) |
| import/export |  | [DO NOT USE](https://google.github.io/styleguide/jsguide.html#file-es6-modules) | [Use](https://github.com/airbnb/javascript#modules) |  |  |
| require\(\) |  | [Custom Solution](https://google.github.io/styleguide/jsguide.html#file-es6-modules) | [DO NOT USE](https://github.com/airbnb/javascript#modules) |  |  |
| Trailing Commas | Required | [Required](https://google.github.io/styleguide/jsguide.html#features-arrays-trailing-comma) | [Required](https://github.com/airbnb/javascript#commas--dangling) |  |  |
| camelCase |  |  | objects, functions, instances |  |  |
| blank |  |  | objects, functions, instances |  |  |

## strict mode

Begin files with:

```javascript
'use strict';
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict\_mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)

## Arrow functions: `() => {}`

```javascript
const a = (param1, param2) => {
  return param1 + param2;

}

const b = (param1, param2) => param1 + param2;
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

## Array

### Test Array

```javascript
Array.isArray(array)
```

This does not work to test if its an array.

```javascript
if (array) {
  // empty arrays evaluate as false
}

if (array && array.length > 0) {
  // you may still want to capture the array
}
```

### Clone an array

```javascript
const clone = array.slice(0);
```

### Iterate keys in an array `(for...in)`

```javascript
  const array = ['x', 'y', 'z'];
  for (const key in array) {
    console.log(key);
  }
```

```text
0
1
2
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in)

### Iterate values in an array `(for...of)`

```javascript
  const array = ['x', 'y', 'z'];
  for (const value of array) {
    console.log(value);
  }
```

```text
x
y
z
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)

### Appending/merging arrays together

```javascript
const array3 = array1.concat(array2);
```

## String

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

### UTF Support

[https://stackoverflow.com/questions/16293923/does-v8-have-unicode-support](https://stackoverflow.com/questions/16293923/does-v8-have-unicode-support) [https://github.com/v8/v8/blob/master/include/v8.h](https://github.com/v8/v8/blob/master/include/v8.h)

## Object

### Clone an object

```javascript
const clone = Object.assign({}, original);
```

 Doesn't do deep cloning.

### Iterate keys in an object `(for...in)`

```javascript
  const object = {x: 'a', y: 'b', z: 'c'}
  for (const key in object) {
    console.log(`${key}: ${object[key]}`);
  }
```

Result:

```text
x: a
y: b
z: c
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)

### Iterate values in an object `(for...of)`

 Do not use \`\(for...of\)\` with \`objects\`. This will fatal with:

Safari:

```text
TypeError: page[Symbol.iterator] is not a function. (In 'page[Symbol.iterator]()', 'page[Symbol.iterator]' is undefined)
```

Chrome: 

```text
Uncaught TypeError: page[Symbol.iterator] is not a function
```

## Set

* Use `size` vs `length`.
* To add: use `add`
* To remove/delete: use `delete`

### Set Cloning

```javascript
const new = new Set(old);
```

Or if enabled:

```javascript
const new = ...old
```

### Set Iteration

```javascript
for (let value of set.values()) {
  ...
}
```

### To Array

```javascript
Array.from(new Set())
```

### Differences

[https://github.com/aizatto/nodejs/blob/master/src/fn.js\#L42](https://github.com/aizatto/nodejs/blob/master/src/fn.js#L42)

```javascript
function setMath<T>(a: Set<T>, b: Set<T>) {
  return {
    remove: [...a].filter(x => !b.has(x)),
    add: [...b].filter(x => !a.has(x)),
  };
}
```

## Async

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async\_function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)

```javascript
async () => {
  await new Promise(...);
  const [
    result1,
    result2,
  ] = await Promise.all([
    new Promise(),
    new Promise(...)],
  );
  return value;
}
```

## `Promise`s

* [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
* [https://github.com/wbinnssmith/awesome-promises](https://github.com/wbinnssmith/awesome-promises)
* [http://bluebirdjs.com/docs/why-promises.html](http://bluebirdjs.com/docs/why-promises.html)

When you start chaining a lot of promises and passing variables around, consider usings `aysnc` instead.

Pay attention to the style, because it's really stupid.

```javascript
const start = new Promise((resolve, reject) => {
  xhr.get(url)
    .success((result) => resolve(result))
    .failure((error) => reject(error));
});

const afterStart = (startResult) => new Promise((resolve, reject) => {
});

start
  .then(afterStart)
  // Always start on a new line, its easier to catch
  // Always use a Promise or only { Promise.all([]) }, its eaiser to catch
  .then() => new Promise((resolve, reject) => {
  })
  .catch((error) => {
    console.log(error);
  });
```

* Always have a `catch()` to ensure you can see all errors.

## `window`

### `window.location.hash`

```javascript
console.log(window.location.hash);
```

Results:

```text
#array
```

Results will always be prefixed with `#`

#### scroll

Scroll to a part of the screen.

```javascript
window.location.hash = '#object'
```

## trailing commas

[http://exploringjs.com/es2016-es2017/ch\_trailing-comma-parameters.html](http://exploringjs.com/es2016-es2017/ch_trailing-comma-parameters.html)

## Regex

* [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp)

### Matching one string

```javascript
"aaaa".match(/[a]/)
```

Result:

```text
["a"]
```

### Matching multiple substrings

```javascript
"a a123a a123a b123b c".match(/a(123)a/g)
```

Result:

```text
["a123", "a123"]
```

Note the trailing `/g`

* You cannot select individual groups while using `g`

### Simple Assert

```javascript
input = "a b c d e";

main(input) {
  ...
}

assert(expected, input) {
  console.log(input);
  actual = main(input);
  result = expected === actual;
  console.log(result);
  if (!result) {
    console.log(actual);
    console.log(expected);
  }
}

// Case 1
assert(expected, input);

// Case 2
assert(expected2, input2);

// Case 3
assert(expected3, input3);
```

## \`\`[`querystring`](https://nodejs.org/api/querystring.html)\`\`

Warning:  `querystring.stringify` does not stringify deeply nested objects.

* GitHub Gist: [Merge Query Strings](https://gist.github.com/aizatto/c1f42416034cf0e3303c85f4dd251334)

## `Class`es

```javascript
class Animal {
  constructor() {
  }
}

class Cat extends Animal {
  constructor(props) {
    super(props)
  }
}
```

## Modules

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

## Cons / Dislikes

* No conventions.
* Not standardized.
* No consistency in online resources.
  * Lots of outdated online resources.
  * The fact that AirBNB has 20 pages on how to write JavaScript is insane.
* No first class Enums
* No types. Can be handled by [Flow](https://github.com/facebook/flow) or [TypeScript](https://www.typescriptlang.org)
* Callback hell \(work around with Promises, `async` and `await`, but its not supported everywhere\)
* Inconsisent: `Array.length` vs `Set.size`
  * Like wtf?
* All the problems of a loosely typed language.
  * Hard to scale as a language, due to no types.
  * Hard to refactor.
* Inconsistencies in coding style amongst the community
* JS Modules are confusing
* Requires high code coverage due to inconsistencies.
* Changing `babel` flags can make your code run differently
  * Requires high code coverage to ensure it does as expected.
* You need tools like `lodash` for basic stuff \(bucketing items in in an array, `groupBy`\)
* Requires a lot of tooling to maintain JavaScript
* Was design for client side browsing, not server side
* It has both `null` and `undefined`
* No native `sprintf`
* Browser support is differet. I ran into a problem with fetch\(\) not being supported. [https://github.com/github/fetch\#browser-support](https://github.com/github/fetch#browser-support)
* Requires a lot of static analysis tools.
  * jshint [http://jshint.com/about/](http://jshint.com/about/) 
  * flow

### Flow vs TypeScript

* [http://djcordhose.github.io/flow-vs-typescript/elm-flow-typescript.html\#/](http://djcordhose.github.io/flow-vs-typescript/elm-flow-typescript.html#/)

#### Flow

[https://flow.org/en/docs/config/](https://flow.org/en/docs/config/)

[https://github.com/facebook/relay/blob/master/.flowconfig](https://github.com/facebook/relay/blob/master/.flowconfig) [https://github.com/facebook/react/blob/master/.flowconfig](https://github.com/facebook/react/blob/master/.flowconfig) [https://github.com/graphql/graphql-js/blob/master/.flowconfig](https://github.com/graphql/graphql-js/blob/master/.flowconfig)

#### ESLINT

## Alternatives

* Go
* [Elixir](/elixir/)

## Frameworks

* [http://graphql.org/code/](http://graphql.org/code/)
* [https://github.com/graphql/graphql-js/](https://github.com/graphql/graphql-js/)
* [https://github.com/graphql/express-graphql](https://github.com/graphql/express-graphql)
* [http://expressjs.com](http://expressjs.com)

### ORM

* [http://docs.sequelizejs.com/en/v3/](http://docs.sequelizejs.com/en/v3/)
* [http://bookshelfjs.org](http://bookshelfjs.org)

## To add

* `async`/`await`

