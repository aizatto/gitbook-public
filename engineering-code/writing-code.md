# Writing Code

* The moment you write code, its already technical debt.
* Every new code is an investment.
* How do you manage your investment?

## Aims for writing code

Balance writing for longevity.

* How long will your code last?

Write for clarity.

Write for simplicity.

* For the long term: simplicity out lives complexity.

Write knowing that it will be read later.

More time will be spent reading and understanding code, than writing it. Reading to writing ratio is really high.

Write so that it is easy to understand.

Write to reduce "WTFs/minute". \[WTFs/minute is the only valid measurement of code quality\]\([http://www.osnews.com/story/19266/WTFs\_m](http://www.osnews.com/story/19266/WTFs_m)"\).

Write with the aim to reduce surprises.

Write code that is easy to test and reproduce.

Write code that is meant to be read, and not meant to solve a problem.

Don't write complex code. Write simple code.

Becareful of death by a thousand cuts/commits/diffs. It is very easy to lose track of the architecture.

Reduce create technical debt.

See [Reviewing Code](/engineering-code/reviewing-code/).

## What is clarity?

* Easy to read
* Consistency
* Naming
* Conventions
* Trust

Goals:

* Increase signal. Reduce noise.
* Reduce petty philsophical disagreements. Avoid bike shed problems.
* Save time, energy and resources for the larger technical problems.

Examples:

* You should not be wasting time, energy, and resource discussing style. Quickly come to an agreement and stick with it. Use a linter. Don't increase noise.

## Writing for a code base of 1,000,000+ Lines

Writing code for a 1,000 line application is very different from writing for 1,000,000 line application.

When the codebase becomes so large, you simply cannot remember everything.

You rely on naming, conventions, and trust.

### Conventions

Understand the conventions already used, and stick to them. It makes it easier to read the code, and get it reviewed.

In a large code base, coding conventions may be different from team to team.

### Consistency

Use linters.

### Don't waste time discussing style

Use linters.

If a discussion about style comes up, quickly agree on something, and implement it in your linter.

### Trust in the code base

You will always be using a library written by someone else. You have to trust that it says it does what it does. If it doesn't, then you have to dive deeper down the rabbit hole.

## 2 biggest problems in programming

* Naming
* Caching
* Off By One Errors

### Naming Good Names \(files, directories, classes, methods\)

#### Avoid Single Letter Variable Names

## Write Code Knowing It Will Be Refactored

Code will always be refactored. Accept this.

## Leave It Better Than You Left It

## Make It Easy To Reproduce

Write code that is easy to test and reproduce.

The easier it is to reproduce. The easier it is to test. The easier it is to test. The more you will test it.

## Small Functions

## Input &gt; Process &gt; Output

### Output can be an Input for another step

### Measure Input &gt; Process &gt; Output

What to Measure:

Input/Output:

* Number of Units
* Before/After state of the process

Process:

* How long did it take
* How mucch processing time is used
* How much memory did it use
* How much bandwidth was used

Output:

* How many were successful
* How many failed
* Why did they fail
* Which failed

### Funnels

When there are many Input &gt; Process &gt; Output, then you have a funnel.

### Break down a Proces

## Handling Errors

### Silent Errors vs Fataling

### Always print IDs

```php
if ($ent === null) {
  printf("Unable to load ent %d", $ent_id);
  exit(1);
}
```

## Write code knowing you will be blamed

Otherwise known as "maintain line history as much as possible".

This is bad because if you wanted to change an argument you would have to change the line history.

```text
printf("Uknown Cop %s %s %s %s", $a, $b, $c, $d);
```

This is better

```text
printf(
  "Unkown Cop %s %s %s %s",
  $a,
  $b,
  $c,
  $d,
);
```

## 80 character limit

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

## Be careful about chaining conditions.

This may dangerous, because it's hard to debug.

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

## Becareful of chains of ternary operators

A chain of ternary operators make it hard to judge what is happening.

Do not do this:

```text
$size = $button === 'submit' ? 'big : 'small';
$text = $button === 'submit'
  ? $l10n->getBigText()
  : $l10n->getSmallText();
$action = $button === 'submit'
  ? '/submit'
  : '/reset'
```

Do this:

```text
if ($button === 'submit') {
  $size = 'big';
  $text = $l10n->getBigText();
  $action = '/submit';
} else {
  $size = 'small';
  $text = $l10n->getSmallText();
  $action = '/reset';
}
```

## Tuples

Sometimes we need to pair two variables together to represent a single datatype. For example `tuple(MetricID, Partner)` which tells us that this represents the `MetricID` for a given `Partner`.

You may want to consider 2 data structures for this:

* `Metric(MetricID)`
* `MetricPartner(Metric/MetricID, Partner)`

It is easier moving from a data structure that manages one data type, to a data structure that manages 2.

Consider having a function in `Metric` which takes in a `Partner` and returns a `MetricPartner`. For example:

```text
  $metric = new Metric($metric_id);
  $metric_partner = $metric->withPartner($partner);
```

## Becareful of enum in Switch statements

If an `enum` is in more than one `switch` statement. Consider making a factory class which returns singleton class for the enum value.

For example, if you only have one instance of this, its ok:

```text
function getName(Color $color) {
  switch($color) {
    case Color::RED:
      return 'Red';

    case Color::BLUE:
      return 'Blue';
  }
}
```

But if you add another function, then make a factory class which returns an instance.

```text
function getRGB(Color $color) {
  switch($color) {
    case Color::RED:
      return '#FF0000';

    case Color::BLUE:
      return '#0000FF';
  }
}
```

Do this instead:

```text
class ColorFactory {
  public static function get(ColorEnum $color) {
    switch ($color) {
      case ColorEnum::RED:
        return ColorRed::get();

      case ColorEnum::Blue:
        return ColorBlue::get();
    }
  }
}

class Color extends Color {
  public function get(ColorEnum $color) {
    switch ($color) {
      case ColorEnum::RED:
        return ColorRed::get();

      case ColorEnum::Blue:
        return ColorBlue::get();
    }
  }
}

abstract class ColorBase extends Color {
  public function getName(): string;
  public function getRGB(): string;
}

final class ColorRed extends Color {
  public function getID(): Color {
    return Color::RED;
  }

  public function getName(): string {
    return 'Red';
  }

  public function getRGB(): string {
    return '#FF0000';
  }
}

final class ColorBlue extends Color {
  public function getID(): Color {
    return Color::Blue;
  }

  public function getName(): string {
    return 'Blue';
  }

  public function getRGB(): string {
    return '#0000FF';
  }
}

function main() {
  $color = ColorFactory::get($color)
  return $color->getName();
}
```

Yes there is more code, but its easier to manage the code. When adding a new Enum you are not required to remember which files to update, the compiler will catch any undefined functions.

## Deep inheritance trees are bad

## Be careful of parameter bags

## Single Responsibility Principle \(SRP\)

## Use intention revealing names

## 2 hardest parts of programming

## Write code that is meant to be read, and not meant to solve a problem

## Duplicating calls is ok.

## Monitoring/Alerts

* How many lines of code are being added?
* Are there alerts on highly sensitive parts of the codebase?

## For user input: consider using Regexes instead of String comparisons

Pros:

* More flexibility in matching strings
* Regexes don't require precise string matching
* Can easily match more than one string, for example to match all branches where `node8` work is done: `/\.*node8/`

Cons:

* Regexes are slightly more time consuming

For example:

```javascript
regex.matches(input)
```

vs

```text
inputs.split(',').some((input) => input === expected);
```

## Scripts

When writing scripts, always leave a file header about what the script does, or link to a proper resource.

For example:

```bash
!/bin/sh
# Reencrypts the keys in our database.
# This is necessary because ....
# http://www.example.com/wiki/details
```

## Logs

Also applies to:

* Deployment History

Consider including:

* Time
* Script used to fire the log
* Server/Hostname the log was created
* Where this log was fired
* Things that make it easy to find the source of the log

