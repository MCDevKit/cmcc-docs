---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: bitwiseNot
---

# bitwiseNot

Performs bitwise NOT operation on a number.

## Arguments

 - a: A number

## Example

```json
{
  "$template": {
    "$comment": "The field below will be -6",
    "test": "{{"{{bitwiseNot(5)"}}}}"
  }
}
```
