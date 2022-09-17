---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: ceil
---

# ceil

Returns the smallest integer greater than or equal to the given number.
## Arguments

- `number` - The number to ceil.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 4",
    "test": "{{"{{ceil(3.6)"}}}}"
  }
}
```
