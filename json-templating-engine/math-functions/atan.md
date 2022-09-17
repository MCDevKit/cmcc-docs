---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: atan
---

# atan

Returns the arctangent of the given number.
## Arguments

- `number` - The number to get the arctangent of.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 45",
    "test": "{{"{{atan(1)"}}}}"
  }
}
```
