---
layout: page
grand_parent: JSON Templating Engine
parent: Type functions
title: asString
---

# asString

Returns the argument as a string.
## Arguments

- `object` - The value to convert.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be \"5\"",
    "test": "{{"{{asString(5)"}}}}"
  }
}
```
