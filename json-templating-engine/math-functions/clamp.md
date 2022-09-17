---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: clamp
---

# clamp

Returns the given number clamped between the given minimum and maximum.
## Arguments

- `number` - The number to clamp.
- `min` - The minimum value.
- `max` - The maximum value.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 5",
    "test": "{{"{{clamp(3, 5, 10)"}}}}"
  }
}
```
