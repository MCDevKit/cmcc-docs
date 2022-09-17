---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: bitshiftRight
---

# bitshiftRight

Returns the bitwise right shift of the given numbers.
## Arguments

- `number` - The number to bitwise right shift.
- `shift` - The number of bits to shift.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 1",
    "test": "{{"{{bitshiftRight(3, 1)"}}}}"
  }
}
```
