# Async & Await / Promises

## Async

### Main function

```typescript
(async () => {
  throw new Error('Hello World');
})().catch((err) => console.error(err));
```

### With Promises

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

