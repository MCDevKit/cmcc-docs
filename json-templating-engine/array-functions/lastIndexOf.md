---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: lastIndexOf
---

# lastIndexOf

Returns index of the last occurrence of given element inside the array or -1 if not found.

## Arguments

 - array: Source array
 - element: Element to find

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 1",
    "test": "{{"{{(1..5).lastIndexOf(2)"}}}}"
  }
}
```
