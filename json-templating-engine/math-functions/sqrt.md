---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: sqrt
---

# sqrt

Returns the square root of the given number.
## Arguments

- `number` - The number to get the square root of.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 3",
    "test": "{{"{{sqrt(9)"}}}}"
  }
}
```
