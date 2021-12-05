# Coding

Example Question:

* Make assumptions
* If they tell you are taking input from STDIN, start by just taking input from a string.
* Write example cases as comments, or part of the code execution. This gives discussion points.
* Explain assumptions about validity of input
* Create an `assert` function, which takes in the `expected` result given an `input`. See [PHP](https://app.gitbook.com/php#simple-assert) or [JS](https://app.gitbook.com/js#simple-assert)

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

##
