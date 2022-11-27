---
layout: page
grand_parent: JSON Templating Engine
parent: Type functions
title: isObject
---

# isObject

Returns whether the argument is an object.
## Arguments

- `object` - The value to check.

## Example

```json
{
  "$scope": {
    "test": {}
  },
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{isObject(test)"}}}}"
  }
}
```
