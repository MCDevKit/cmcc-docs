---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: mod
---

# mod

Returns the remainder of the first number divided by the second number.
## Arguments

- `number` - The number to divide.
- `divisor` - The number to divide by.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 1",
    "test": "{{"{{mod(5, 2)"}}}}"
  }
}
```
