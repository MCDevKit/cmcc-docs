---
layout: page
grand_parent: JSON Templating Engine
parent: Functions
title: hexToArray
---

# hexToArray

`hexToArray` is a function, that returns a color array from hex color string in first argument.

## Arguments

 - hex color: A color in hex format

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [0.2, 0.4, 0.6, 1]",
    "test": "{{hexToArray('#336699')}}"
  }
}
```