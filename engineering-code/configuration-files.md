# Configuration Files

## Formats

### .env

[https://www.npmjs.com/package/dotenv](https://www.npmjs.com/package/dotenv)

Properties:

* Simple configuration
* Values can only be a string or a number
* No complicated values
* Useful when making minor flags or changes
* Human readable

Example:

{% code title=".env" %}
```bash
NODE_ENV=production
PORT=3001
```
{% endcode %}

### JSON or JSON5

If possible use JSON5 over JSON.

From [https://github.com/json5/json5](https://github.com/json5/json5)

> The JSON5 Data Interchange Format \(JSON5\) is a superset of [JSON](https://tools.ietf.org/html/rfc7159) that aims to alleviate some of the limitations of JSON by expanding its syntax to include some productions from [ECMAScript 5.1](https://www.ecma-international.org/ecma-262/5.1/).

Properties:

* Nested configuration
* Uses an already familiar programming paradigm
* Human readable

Example:

{% code title="example.json5" %}
```javascript
{
  // comments
  unquoted: 'and you can quote me on that',
  singleQuotes: 'I can use "double quotes" here',
  lineBreaks: "Look, Mom! \
No \\n's!",
  hexadecimal: 0xdecaf,
  leadingDecimalPoint: .8675309, andTrailing: 8675309.,
  positiveSign: +1,
  trailingComma: 'in objects', andIn: ['arrays',],
  "backwardsCompatible": "with JSON",
}
```
{% endcode %}

### XML

Properties:

* Complicated
* Overly verbose
* Useful for computers interfacing with each other

### YAML \(YAML Ain't Markup Language or Yet Another Markup Language\)

[https://yaml.org/](https://yaml.org/)

Properties:

* Can get complex with the "repeated nodes" syntax
* Spacing is important, which can throw off the configuration
* Isn't immediately obvious when something is a list/array or a map

### INI

[https://en.wikipedia.org/wiki/INI\_file](https://en.wikipedia.org/wiki/INI_file)

Properties:

* Cannot be deeply nested

```text
; last modified 1 April 2001 by John Doe
[owner]
name=John Doe
organization=Acme Widgets Inc.

[database]
; use IP address in case network name resolution is not working
server=192.0.2.62     
port=143
file="payroll.dat"
```

## Should you mix formats?

### Reasons to mix: Yes

Example: mixing .env and JSON5

When you need a mix of simple and complex data structures?

JSON objects should only be read once.

Environment variables can be read multiple times in the system.

Limit it to just two.

### Reasons not to mix: No

Don't mix too many formats. Too many different rules to remember. Or use different format for communication between services \(ie: JSON, or XML files\)

## Should you create your own?

No. Unless you have a really good reason.

You have to create a parser.

