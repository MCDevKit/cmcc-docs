---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: count
---

# count

Returns the number of elements in an array.

## Arguments

 - array: Source array
 - predicate(element, index): (optional) Lambda, that should return whether an element should be counted

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 3",
    "test": "{{"{{(0..4).count(x => mod(x, 2) == 0)"}}}}"
  }
}
```
