# Object

## Clone an object

```javascript
const clone = Object.assign({}, original);
```

Note: Doesn't do deep cloning. Use `lodash` or `underscore`

## Iterate keys in an object `(for...in)`

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

## Iterate values in an object `(for...of)`

 Do not use \`\(for...of\)\` with \`objects\`. This will fatal with:

Safari:

```text
TypeError: page[Symbol.iterator] is not a function. (In 'page[Symbol.iterator]()', 'page[Symbol.iterator]' is undefined)
```

Chrome: 

```text
Uncaught TypeError: page[Symbol.iterator] is not a function
```

## 

