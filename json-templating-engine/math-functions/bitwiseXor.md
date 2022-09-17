---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: bitwiseXor
---

# bitwiseXor

Returns the bitwise XOR of the given numbers.
## Arguments

- `number1` - The first number to bitwise XOR.
- `number2` - The second number to bitwise XOR.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 1",
    "test": "{{"{{bitwiseXor(3, 2)"}}}}"
  }
}
```
