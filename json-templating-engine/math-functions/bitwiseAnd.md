---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: bitwiseAnd
---

# bitwiseAnd

Performs bitwise AND operation on two numbers.

## Arguments

 - a: First number
 - b: Second number

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 1",
    "test": "{{"{{bitwiseAnd(5, 3)"}}}}"
  }
}
```
