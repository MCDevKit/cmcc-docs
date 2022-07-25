---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: min
---

# min

Returns the element, for which the predicate will return the minimum value or null if the array is empty.

## Arguments

 - array: Source array
 - predicate(element, index): Lambda, that should return a number to compare. If none provided, it will use identity lambda (`x => x`)

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 0",
    "test": "{{"{{(0..4).min()"}}}}"
  }
}
```
