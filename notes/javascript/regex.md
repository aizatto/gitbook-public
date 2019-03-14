# Regex

* [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp)

## Matching one string

```javascript
"aaaa".match(/[a]/)
```

Result:

```text
["a"]
```

## Matching multiple substrings

```javascript
"a a123a a123a b123b c".match(/a(123)a/g)
```

Result:

```text
["a123", "a123"]
```

Note the trailing `/g`

* You cannot select individual groups while using `g`

