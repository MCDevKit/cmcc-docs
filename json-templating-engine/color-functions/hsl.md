---
layout: page
grand_parent: JSON Templating Engine
parent: Color functions
title: hsl
---

# hsl

Creates a new color from hue, saturation and lightness values.
## Arguments

- `hsl` - The array of hue, saturation and lightness values.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [0, 255, 0]",
    "test": "{{"{{hsl([120, 1, 0.5])"}}}}"
  }
}
```
