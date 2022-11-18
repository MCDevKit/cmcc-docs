---
layout: page
grand_parent: JSON Templating Engine
parent: Type functions
title: isBoolean
---

# isBoolean

Returns whether the argument is a boolean.
## Arguments

- `object` - The value to check.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{isBoolean(true)"}}}}"
  }
}
```
