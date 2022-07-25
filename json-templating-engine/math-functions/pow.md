---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: pow
---

# pow

Returns the value of the first argument raised to the power of the second argument.

## Arguments

 - a: Base
 - b: Exponent

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 16",
    "test": "{{"{{pow(4, 2)"}}}}"
  }
}
```
