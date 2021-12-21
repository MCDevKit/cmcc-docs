---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: bitwiseXor
---

# bitwiseXor

Performs bitwise XOR (exclusive OR) operation on two numbers.

## Arguments

 - a: First number
 - b: Second number

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 6",
    "test": "{{"{{bitwiseXor(5, 3)"}}}}"
  }
}
```
