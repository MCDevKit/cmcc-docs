---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: flatMap
---

# flatMap

Returns a new array, where every array from lambda is merged into source array.

## Arguments

 - array: Source array
 - lambda(element, index): Lambda, that should return an array to merge. If none provided, it will use identity lambda (`x => x`)

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [1, 2, 3, 4]",
    "test": "{{"{{[[1, 2], 3, [4]].flatMap()"}}}}"
  }
}
```
