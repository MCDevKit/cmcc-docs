---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: acos
---

# acos

Returns the arccosine of the given number.
## Arguments

- `number` - The number to get the arccosine of.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 45.008651662837984",
    "test": "{{"{{acos(0.707)"}}}}"
  }
}
```
