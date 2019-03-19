# fetch

> The Fetch API provides an interface for fetching resources \(including across the network\). It will seem familiar to anyone who has used [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest), but the new API provides a more powerful and flexible feature set.

* [https://developer.mozilla.org/en-US/docs/Web/API/Fetch\_API/Using\_Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)

## **Using in Browsers**

Not supported on all browsers. You can polyfill using `watchwg-fetch`

[https://npmcompare.com/compare/node-fetch,whatwg-fetch](https://npmcompare.com/compare/node-fetch,whatwg-fetch)

## Using in Node.js

* [https://www.npmjs.com/package/node-fetch](https://www.npmjs.com/package/node-fetch)

```bash
yarn add node-fetch
```

Importing:

{% code-tabs %}
{% code-tabs-item title="fetch-import-success.ts" %}
```typescript
import fetch from 'node-fetch';
```
{% endcode-tabs-item %}
{% endcode-tabs %}

If you use webpack, the following will work locally, but fail when deployed in webpack.

{% code-tabs %}
{% code-tabs-item title="fetch-webpack-import-fail.ts" %}
```typescript
import * as fetch from 'node-fetch';
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Text:

{% code-tabs %}
{% code-tabs-item title="fetch-text.ts" %}
```typescript
const response = await fetch(url);
console.log(response);
const text = await response.text();
```
{% endcode-tabs-item %}
{% endcode-tabs %}

`response`:

{% code-tabs %}
{% code-tabs-item title="fetch-text-response.ts" %}
```javascript
{
  ok true,
  status: 200,
  ...
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## JSON:

{% code-tabs %}
{% code-tabs-item title="fetch-json.ts" %}
```javascript
const response = await fetch(url);
const json = await response.json();
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Errors Handling

* No errors are thrown.
* No need for try/catch

{% code-tabs %}
{% code-tabs-item title="fetch-error.ts" %}
```typescript
const response = await fetch(url);
console.log(response);
if (!response.ok) {
  ...
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

`response`:

{% code-tabs %}
{% code-tabs-item title="fetch-error-response.json" %}
```javascript
{
  ok false,
  status: 404,
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

