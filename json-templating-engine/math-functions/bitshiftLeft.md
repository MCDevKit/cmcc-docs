---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: bitshiftLeft
---

# bitshiftLeft

Returns the bitwise left shift of the given numbers.
## Arguments

- `number` - The number to bitwise left shift.
- `shift` - The number of bits to shift.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 12",
    "test": "{{"{{bitshiftLeft(3, 2)"}}}}"
  }
}
```
