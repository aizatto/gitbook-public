# Create Searchable Names

You will always use tools to do code lookup \(grep, ack, GitHub\).

Making them easier to find, increases their visibility.

## Example: "unshareable" vs "unsharable"

Neither "unshareable" or "unsharable" are real English words.

unshareable:

* google \(define:unshareable\), nothing
* [https://www.dictionary.com/browse/unshareable](https://www.dictionary.com/browse/unshareable) exists
* [https://www.yourdictionary.com/unshareable](https://www.yourdictionary.com/unshareable) Impossible to share.
* [https://www.oxfordlearnersdictionaries.com/spellcheck/english/?q=unshareable](https://www.oxfordlearnersdictionaries.com/spellcheck/english/?q=unshareable) does not exist
* [https://www.definitions.net/definition/unshareable](https://www.definitions.net/definition/unshareable) Impossible to share.
* my macOS says "unshareable" is a spelling mistake, without a good suggestion
  * does not exist in `/usr/share/dict/words`

unsharable:

* google \(define:unsharable\), nothing
* [https://www.dictionary.com/browse/unsharable](https://www.dictionary.com/browse/unsharable) exists
* [https://www.yourdictionary.com/unsharable](https://www.yourdictionary.com/unsharable) fails
* [https://www.definitions.net/definition/unsharable](https://www.definitions.net/definition/unsharable) does not exist
* my macOS says "unsharable" is legit, but if you right-click and do "Look up in Dictionary" it doesn't pull out anything
  * exists in `/usr/share/dict/words`

Resolution: chose "unshareable"

* Visually looks correct
* Can be found when searching for "share"

## References

* [Clean Code](https://amzn.to/2EG7ypq): Meaningful Names &gt; Use Searchable Names

