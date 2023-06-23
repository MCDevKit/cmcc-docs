---
layout: page
grand_parent: JSON Templating Engine
parent: Color functions
title: greyscale
---

# greyscale

Sets a gray color with the same lightness as the input color.
## Arguments

- `color` - The color to convert to greyscale as RGB array.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [0.6, 0.6, 0.6]",
    "test": "{{"{{greyscale([0.3, 0.6, 0.9])"}}}}"
  }
}
```
