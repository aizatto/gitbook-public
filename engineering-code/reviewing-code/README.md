# Reviewing Code

Reviews should always provide constructive feedback.

When reviewing, always suggest a better possible state.

Review for clarity.

Review knowing that it will be read later.

More time will be spent reading and understanding code, than writing it. Reading to writing ratio is really high.

Review so that it is easier to understand.

Review to reduce "WTFs/minute". [WTFs/minute is the only valid measurement of code quality.](http://www.osnews.com/story/19266/WTFs\_m)

Review with the aim to reduce surprises.

Review code that is easy to test and reproduce.

Don't Review complex code. Review simple code.

Becareful of death by a thousand cuts/commits/diffs. It is very easy to lose track of the architecture.

Don't create technical debt.

See ["Writing Code"](https://app.gitbook.com/writing-code/).

## Overview

The hardest part about writing code is reviewing it.

Reviewing code is hard because:

* it takes more effort than writing it.
* you have to understand the context of why this commit is required. What files or frameworks it is using.

To write about:

* Consider the architecture.
* Are they using the descriptive names (variables, functions, classes, etc...)?
* Check the directory structure. It's really easy to miss this.
* Dont blame break history.

### Death by a thousand cuts/commits/diffs

Becareful of death by a thousand cuts/commits/diffs. It is very easy to lose track of the architecture of a code base.

### Don't pollute commit history

Commit history is really important in learning and debugging code. It is important that the commit history is kept as clean as possible.

See "Commit Messages".

Do not just change code to change the style of the code. Unless of course the style is really bad. If the style of the code is consistent with the codebase. Don't change the style. Don't go out of style. Changing the code makes you lose blame.

#### Consider blame history

**Always add trailing commas**

If your programming language supports trailing commas. Always include them.

This means that if you ever have to add an additional element/argument to the list, you dont have to change that line.

#### Consider file history

Take for example, you are just adding new lines to another file which you don't use. New lines look harmless, but they can pollute the file history. If someone were to look at the file history there would be an entry for the erroneous lines you added.

### Test Plan

How easy is it to reproduce the commit/diff? The easier it is to reproduce, the better it is.

Check for:

* screenshots (if applicable)
* URLs to anything relevant
* what configurations need to be changed
* shell commands ran

### Don't create technical debt

## Things to communicate as a reviewer

* If things are a nonblocker
* If things can be fixed in another PR
  * This allows them to maintain momentum

## Resources

* [https://mtlynch.io/human-code-reviews-1/](https://mtlynch.io/human-code-reviews-1/)
* [https://www.netlify.com/blog/2020/03/05/feedback-ladders-how-we-encode-code-reviews-at-netlify/](https://www.netlify.com/blog/2020/03/05/feedback-ladders-how-we-encode-code-reviews-at-netlify/)
* [https://google.github.io/eng-practices/review/reviewer/](https://google.github.io/eng-practices/review/reviewer/)
