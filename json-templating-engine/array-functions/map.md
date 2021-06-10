---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: map
---

# map

Returns a new array, where every element is mapped to another value using provided lambda.

## Arguments

 - array: Source array
 - lambda: Lambda, that should return new element value

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [0, 2, 4, 6, 8]",
    "test": "{{"{{map(0..4, x => x => x * 2)}}"}}"
  }
}
```