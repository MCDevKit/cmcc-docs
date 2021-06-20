---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: findFirst
---

# findFirst

Returns the first element from an array filtered by the predicate.

## Arguments

 - array: Source array
 - predicate: Lambda, that should return whether an element should remain

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 0",
    "test": "{{"{{findFirst(0..4, x => mod(x, 2) == 0)}}"}}"
  }
}
```
