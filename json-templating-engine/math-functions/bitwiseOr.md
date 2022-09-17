---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: bitwiseOr
---

# bitwiseOr

Returns the bitwise OR of the given numbers.
## Arguments

- `number1` - The first number to bitwise OR.
- `number2` - The second number to bitwise OR.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 3",
    "test": "{{"{{bitwiseOr(3, 2)"}}}}"
  }
}
```
