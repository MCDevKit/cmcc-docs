---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: bitwiseNot
---

# bitwiseNot

Returns the bitwise NOT of the given number.
## Arguments

- `number` - The number to bitwise NOT.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be -4",
    "test": "{{"{{bitwiseNot(3)"}}}}"
  }
}
```
