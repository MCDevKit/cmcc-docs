---
layout: page
grand_parent: JSON Templating Engine
parent: Color functions
title: arrayToHex
---

# arrayToHex

Converts an array of RGB(A) values to a hex color. If the array has transparency, the hex color will be in the format #AARRGGBB.
## Arguments

- `array` - The RGB(A) array to convert.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be '#336699'",
    "test": "{{"{{arrayToHex([0.2, 0.4, 0.6])"}}}}"
  }
}
```
