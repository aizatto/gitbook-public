# fetch

* [https://developer.mozilla.org/en-US/docs/Web/API/Fetch\_API/Using\_Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
* [https://www.npmjs.com/package/node-fetch](https://www.npmjs.com/package/node-fetch)

## Text:

```typescript
const response = await fetch(url);
const json = await response.text();
console.log(response);
```

`response`:

```javascript
{
  ok true,
  status: 200,
  ...
}
```

## JSON:

```javascript
const response = await fetch(url);
const json = await response.json();
```

## Errors Handling

* No errors are thrown.
* No need for try/catch

```typescript
const response = await fetch(url);
console.log(response);
if (!response.ok) {
  ...
}
```

`response`:

```javascript
{
  ok false,
  status: 404,
}
```

