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

## String

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

### UTF Support

[https://stackoverflow.com/questions/16293923/does-v8-have-unicode-support](https://stackoverflow.com/questions/16293923/does-v8-have-unicode-support) [https://github.com/v8/v8/blob/master/include/v8.h](https://github.com/v8/v8/blob/master/include/v8.h)

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

## Flow vs TypeScript

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

