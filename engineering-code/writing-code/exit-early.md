# Exit Early

Discourage:

```javascript
if () {
  ...
  return false;
} else {
  ...
  return true;
}
```

Encourage:

```javascript
if () {
  ...
  return false;
}

...

return true;
```

Reasons to exit early:

* Process of elimination
* Reduces cognitive load
* Reduces indents
* We know success will always be at the end
* Structures your functions:
  * Validation/error handling at the beginning
  * Successful at the end

Resources

* [https://news.ycombinator.com/item?id=16678209](https://news.ycombinator.com/item?id=16678209)
* [https://www.itamarweiss.com/personal/2018/02/28/return-early-pattern.html](https://www.itamarweiss.com/personal/2018/02/28/return-early-pattern.html)
* [https://softwareengineering.stackexchange.com/questions/18454/should-i-return-from-a-function-early-or-use-an-if-statement](https://softwareengineering.stackexchange.com/questions/18454/should-i-return-from-a-function-early-or-use-an-if-statement)
* [https://blog.timoxley.com/post/47041269194/avoid-else-return-early](https://blog.timoxley.com/post/47041269194/avoid-else-return-early)

Arguments against:

* single exit point
  * [https://www.tomdalling.com/blog/coding-tips/coding-tip-have-a-single-exit-point/](https://www.tomdalling.com/blog/coding-tips/coding-tip-have-a-single-exit-point/)

