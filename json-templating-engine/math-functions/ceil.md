---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: ceil
---

# ceil

Returns an integer number rounded up.

## Arguments

 - number: A number to ceil

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 4",
    "test": "{{"{{ceil(3.3)}}"}}"
  }
}
```
