---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: mod
---

# mod

Returns the remainder (modulo) of the two arguments.

## Arguments

 - number: A number
 - denominator: A denominator

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 1",
    "test": "{{"{{mod(5, 2)"}}}}"
  }
}
```
