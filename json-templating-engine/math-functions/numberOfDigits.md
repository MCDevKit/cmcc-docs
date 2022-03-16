---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: numberOfDigits
---

# numberOfDigits

Returns the number of digits of a number.

## Arguments

 - a: A number

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 3",
    "test": "{{"{{numberOfDigits(123)"}}}}"
  }
}
```
