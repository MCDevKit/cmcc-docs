---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: filter
---

# filter

Returns an array that is filtered based on a predicate.

## Arguments

 - array: Source array
 - predicate: Lambda, that should return whether an element should remain

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [0, 2, 4]",
    "test": "{{"{{filter(0..4, x => mod(x, 2) == 0)"}})}}"
  }
}
```