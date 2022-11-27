---
layout: page
grand_parent: JSON Templating Engine
parent: Type functions
title: asBoolean
---

# asBoolean

Returns the argument as a boolean.
## Arguments

- `object` - The value to convert.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{asBoolean('true')"}}}}"
  }
}
```
