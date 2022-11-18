---
layout: page
grand_parent: JSON Templating Engine
parent: Type functions
title: isString
---

# isString

Returns whether the argument is a string.
## Arguments

- `object` - The value to check.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{isString('asd')"}}}}"
  }
}
```
