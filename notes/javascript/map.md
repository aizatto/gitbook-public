# Map

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)

Examples are in TypeScript.

## Use function setters and getters

```typescript
const map: Map<string, string> = new Map();
// Do not use []
// This is bad
map["key"] = "value";

// Do this instead
map.get(key, value);
```



