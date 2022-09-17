---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: atan2
---

# atan2

Returns the arctangent of the given numbers.
## Arguments

- `y` - The first number to get the arctangent of.
- `x` - The second number to get the arctangent of.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 45",
    "test": "{{"{{atan2(1, 1)"}}}}"
  }
}
```
