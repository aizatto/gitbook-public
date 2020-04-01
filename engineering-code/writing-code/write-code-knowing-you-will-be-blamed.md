# Write Code Knowing You Will be Blamed

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

Resolution:

* Always leave trailing commas
* For long arguments, consider splitting them over multiple lines

