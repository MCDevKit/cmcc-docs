---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: sin
---

# sin

Returns the sine of the given number.
## Arguments

- `number` - The number to get the sine of.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 0.7071067811865475",
    "test": "{{"{{sin(45)"}}}}"
  }
}
```
