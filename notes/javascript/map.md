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

## Iterating `Map` with `for..of`

Taken from [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Map\#Iterating\_Map\_with\_for..of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map#Iterating_Map_with_for..of)

```javascript
var myMap = new Map();
myMap.set(0, 'zero');
myMap.set(1, 'one');
for (var [key, value] of myMap) {
  console.log(key + ' = ' + value);
}
// 0 = zero
// 1 = one

for (var key of myMap.keys()) {
  console.log(key);
}
// 0
// 1

for (var value of myMap.values()) {
  console.log(value);
}
// zero
// one

for (var [key, value] of myMap.entries()) {
  console.log(key + ' = ' + value);
}
// 0 = zero
// 1 = one
```

