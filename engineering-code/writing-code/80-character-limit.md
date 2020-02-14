# 80 character limit

Pros:

* Forces you to focus on legibility.
  * Emphasis on short.
* Encourages preserving source control blame
* Long lines raises concerns on naming

Cons:

* Some languages may not be suitable for 80 characters.
* Can make some functions or conditions longer
  * When writing conditions, consider breaking them into multiple conditions. See below for reasoning.
* The focus on short may may become bad.
  * Example: Bad variable names.
  * Example: Too many small functions. Makes it difficult to understand flow.
  * Aim for balance.

Considerations:

* Not everyone has the same screen size as you
* Choose the lowest common denominator
  * How many characters can comfortably in the tools you use?
    * GitHub [split diff views](https://github.com/aizatto/character-length/commit/bae8f00feda5b832aa6fe162460968d8eaf040a5) 
      * 13" MacBookPro on "More Space" Resolution \(1680x1050\) can only comfortably show 104 characters
      * 1280px width can comfortably show 87 characters.
        * General width of my windows when tiled on a [desktop monitor](../../notes/archive/displays-monitors.md)
    * See my [testing](https://github.com/aizatto/character-length)

Exceptions:

* URLs. Always try to use full URLs as much as possible as it helps the reader to intuit the purpose of the URL.

Notes:

* Python recommends [79 characters](https://www.python.org/dev/peps/pep-0008/#maximum-line-length)
* I've [tested out character length](https://github.com/aizatto/character-length) on different sites

