---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: floor
---

# floor

Returns the largest integer less than or equal to the given number.
## Arguments

- `number` - The number to floor.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 3",
    "test": "{{"{{floor(3.6)"}}}}"
  }
}
```
