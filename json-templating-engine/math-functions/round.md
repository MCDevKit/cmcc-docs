---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: round
---

# round

Returns the nearest number with specified precision.

## Arguments

 - number: A number to round
 - precision: A number of decimal places. If none specified, it will round to the nearest integer.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 3.142",
    "test": "{{"{{round(3.1415, 3)}}"}}"
  }
}
```
