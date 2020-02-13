# 80 character limit

Pros:

* Forces you to focus on legibility.
  * Emphasis on short.
* Encourages preserving source control blame

Cons:

* Some languages may not be suitable for 80 characters.
* Can make some functions or conditions longer
  * When writing conditions, consider breaking them into multiple conditions. See below for easoning.
* The focus on short may may become bad.
  * Example: Bad variable names.
  * Example: Too many small functions. Makes it difficult to understand flow.
  * Aim for balance.

Exceptions:

* URLs. Always try to use full URLs as much as possible as it helps the reader to intuit the purpose of the URL.

Notes:

* Python recommends [79 characters](https://www.python.org/dev/peps/pep-0008/#maximum-line-length)
* I've [tested out character length](https://github.com/aizatto/character-length) on different sites

