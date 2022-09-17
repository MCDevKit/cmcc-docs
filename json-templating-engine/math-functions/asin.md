---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: asin
---

# asin

Returns the arcsine of the given number.
## Arguments

- `number` - The number to get the arcsine of.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 44.991348337162016",
    "test": "{{"{{asin(0.707)"}}}}"
  }
}
```
