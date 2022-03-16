---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: bitshiftLeft
---

# bitshiftLeft

Performs signed left shift operation on a number by number of positions.

## Arguments

 - a: A number to shift
 - b: Number of positions to shift

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 4",
    "test": "{{"{{bitshiftLeft(1, 2)"}}}}"
  }
}
```
