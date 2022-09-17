---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: abs
---

# abs

Returns the absolute value of the given number.
## Arguments

- `number` - The number to get the absolute value of.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 3",
    "test": "{{"{{abs(-3)"}}}}"
  }
}
```
