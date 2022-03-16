---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: bitshiftRight
---

# bitshiftRight

Performs signed right shift operation on a number by number of positions.

## Arguments

 - a: A number to shift
 - b: Number of positions to shift

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 1",
    "test": "{{"{{bitshiftRight(4, 2)"}}}}"
  }
}
```
