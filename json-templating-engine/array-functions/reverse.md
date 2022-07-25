---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: reverse
---

# reverse

Returns an array with reversed order.

## Arguments

 - array: Source array

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [4, 3, 2, 1, 0]",
    "test": "{{"{{(0..4).reverse()"}}}}"
  }
}
```
