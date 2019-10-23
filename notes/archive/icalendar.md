---
description: >-
  This is regarding the: Internet Calendaring and Scheduling Core Object
  Specification (iCalendar)
---

# iCalendar

* [https://tools.ietf.org/html/rfc5545](https://tools.ietf.org/html/rfc5545)
* [https://en.wikipedia.org/wiki/ICalendar](https://en.wikipedia.org/wiki/ICalendar)
* [https://icalendar.org/](https://icalendar.org/)
* [https://github.com/aizatto/ical-debugger](https://github.com/aizatto/ical-debugger)
  * [https://aizatto.github.io/ical-debugger/](https://aizatto.github.io/ical-debugger/)

## Best Practices

Use VALARMs to set reminders \( 3.6.6, page 70\)

> A "VALARM" calendar component is a grouping of component properties that is a reminder or alarm for an event or a to-do. For example, it may be used to define a reminder for a pending event or an overdue to-do.

Example:

```text
BEGIN:VALARM
ACTION:DISPLAY
TRIGGER:-PT5M
DESCRIPTION:This is an event reminder
END:VALARM
```



