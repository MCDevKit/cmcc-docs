---
layout: page
grand_parent: JSON Templating Engine
parent: Type functions
title: asNumber
---

# asNumber

Returns the argument as a number.
## Arguments

- `object` - The value to convert.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 5",
    "test": "{{"{{asNumber('5')"}}}}"
  }
}
```
