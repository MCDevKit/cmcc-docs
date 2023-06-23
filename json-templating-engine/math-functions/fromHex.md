---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: fromHex
---

# fromHex

Returns the given hexadecimal string as a number.
## Arguments

- `string` - The hexadecimal string to convert to a number.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 123",
    "test": "{{"{{fromHex('7b')"}}}}"
  }
}
```
