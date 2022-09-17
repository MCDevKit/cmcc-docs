---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: pow
---

# pow

Returns the given number raised to the given power.
## Arguments

- `number` - The number to raise to the given power.
- `power` - The power to raise the given number to.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 27",
    "test": "{{"{{pow(3, 3)"}}}}"
  }
}
```
