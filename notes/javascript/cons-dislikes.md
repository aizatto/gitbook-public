# Cons/Dislikes

* No conventions.
* Not standardized.
* No consistency in online resources.
  * Lots of outdated online resources.
  * The fact that AirBNB has 20 pages on how to write JavaScript is insane.
* No first class Enums
* No types. Can be handled by [Flow](https://github.com/facebook/flow) or [TypeScript](https://www.typescriptlang.org)
* Callback hell \(work around with Promises, `async` and `await`, but its not supported everywhere\)
* Inconsisent: `Array.length` vs `Set.size`
  * Like wtf?
* All the problems of a loosely typed language.
  * Hard to scale as a language, due to no types.
  * Hard to refactor.
* Inconsistencies in coding style amongst the community
* JS Modules are confusing
* Requires high code coverage due to inconsistencies.
* Changing `babel` flags can make your code run differently
  * Requires high code coverage to ensure it does as expected.
* You need tools like `lodash` for basic stuff \(bucketing items in in an array, `groupBy`\)
* Requires a lot of tooling to maintain JavaScript
* Was design for client side browsing, not server side
* It has both `null` and `undefined`
* No native `sprintf`
* Browser support is inconsistent.
  * I ran into a problem with fetch\(\) not being supported. [https://github.com/github/fetch\#browser-support](https://github.com/github/fetch#browser-support)
* Requires a lot of static analysis tools.
  * jshint [http://jshint.com/about/](http://jshint.com/about/) 
  * flow
* See Node.js's creator Ryan Dahl's "[10 Things I Regret About Node.js](https://www.youtube.com/watch?v=M3BM9TB-8yA)"

What does this return?

```javascript
"some string".match(/some regex/)
```

It's an Array with properties of `index` and `input`. 

Things which increase the JavaScript environments complexity:

* Requiring the use of new features via Babel
* Requiring WebPack to bundle for frontend
* Module systems
* Inconsistent environments
  * Browser development, so many browser versions
  * Node, webpack vs everything else

#### Array.flat

`Array.flat` only works in Node.js 11+

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/flat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flat)

#### Array.values\(\) is different from Object.values\(\)

`Object.values(object)` returns an array of values

`array.values()` returns an iterator

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/values)

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/values)

