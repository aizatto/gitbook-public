# Array

* [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

## Test Array

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

## Clone an array

```javascript
const clone = array.slice(0);
```

## Iterate keys in an array `(for...in)`

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

## Iterate values in an array `(for...of)`

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

## Appending/merging arrays together

Reuse Array:

```javascript
array1.push(...array2);
```

New Array:

```javascript
const array3 = array1.concat(array2);
```

