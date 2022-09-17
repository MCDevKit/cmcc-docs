---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: cos
---

# cos

Returns the cosine of the given number.
## Arguments

- `number` - The number to get the cosine of.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 0.7071067811865476",
    "test": "{{"{{cos(45)"}}}}"
  }
}
```
