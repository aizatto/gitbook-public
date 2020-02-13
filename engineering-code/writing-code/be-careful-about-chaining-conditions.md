# Be careful about chaining conditions

This may dangerous, because it's harder to debug.

For example:

```javascript
return
  expected.key === actual.key &&
  expected.value === actual.value &&
  expected.concern === actual.concern;
```

If we broke it down to multiple `if` conditions it makes it easier to debug.

```javascript
if (expected.key === actual.key) {
  return false;
}

if (expected.value === actual.value) {
  return false;
}

if (expected.concern === actual.concern) {
  return false;
}

return true;
```

Pros for using multiple conditions:

* If you use `Exception`s instead of `return` statements, you can easily get a stack trace which is extremly useful.
* Easier usage of `print` style debugging.

Cons for using multiple `if` conditions:

* Longer function statements.

