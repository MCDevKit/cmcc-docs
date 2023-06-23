---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: toHex
---

# toHex

Returns the given number as a hexadecimal string.
## Arguments

- `number` - The number to convert to a hexadecimal string.
- `digits` - (optional) The number of digits to pad the hexadecimal string with.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 007b",
    "test": "{{"{{toHex(123, 4)"}}}}"
  }
}
```
