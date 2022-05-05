---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: range
---

# range

Returns all indices of the array.

## Arguments

 - array: Source array

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [0, 1, 2, 3, 4]",
    "test": "{{"{{(4..8).range()"}}}}"
  }
}
```
