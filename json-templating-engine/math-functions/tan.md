---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: tan
---

# tan

Returns the tangent of the given number.
## Arguments

- `number` - The number to get the tangent of.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 1",
    "test": "{{"{{tan(45)"}}}}"
  }
}
```
