---
layout: page
grand_parent: JSON Templating Engine
parent: Type functions
title: isArray
---

# isArray

Returns whether the argument is an array.
## Arguments

- `object` - The value to check.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{isArray([])"}}}}"
  }
}
```
