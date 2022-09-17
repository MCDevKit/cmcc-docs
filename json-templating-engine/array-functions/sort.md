---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: sort
---

# sort

Sorts the given array
## Arguments

- `array` - The array to sort
- `selector(element, index)` - (optional) The selector to apply to each element before summing

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [1, 2, 3, 5, 8, 10]",
    "test": "{{"{{[2, 3, 1, 5, 8, 10].sort()"}}}}"
  }
}
```
