---
description: Rules I haven't formatted properly
---

# Other rules

## 2 biggest problems in programming

* Naming
* Caching
* Off By One Errors

### Naming Good Names \(files, directories, classes, methods\)

#### Avoid Single Letter Variable Names

## Leave It Better Than You Left It

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
* How much processing time is used
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

## 

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

## Logs

Also applies to:

* Deployment History

Consider including:

* Time
* Script used to fire the log
* Server/Hostname the log was created
* Where this log was fired
* Things that make it easy to find the source of the log

