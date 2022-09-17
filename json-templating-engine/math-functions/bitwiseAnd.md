---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: bitwiseAnd
---

# bitwiseAnd

Returns the bitwise AND of the given numbers.
## Arguments

- `number1` - The first number to bitwise AND.
- `number2` - The second number to bitwise AND.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 2",
    "test": "{{"{{bitwiseAnd(3, 2)"}}}}"
  }
}
```
