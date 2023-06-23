---
layout: page
grand_parent: JSON Templating Engine
parent: Color functions
title: hexToArray
---

# hexToArray

Converts a hex color to an array of RGBA values.
## Arguments

- `hex` - The hex color to convert.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [0.2, 0.4, 0.6, 1]",
    "test": "{{"{{hexToArray('#336699')"}}}}"
  }
}
```
