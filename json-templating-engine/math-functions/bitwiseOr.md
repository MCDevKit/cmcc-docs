---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: bitwiseOr
---

# bitwiseOr

Performs bitwise OR operation on two numbers.

## Arguments

 - a: First number
 - b: Second number

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 7",
    "test": "{{"{{bitwiseOr(5, 3)"}}}}"
  }
}
```
