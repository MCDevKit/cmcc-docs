---
layout: page
grand_parent: JSON Templating Engine
parent: Type functions
title: isNumber
---

# isNumber

Returns whether the argument is a number.
## Arguments

- `object` - The value to check.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{isNumber(1)"}}}}"
  }
}
```
