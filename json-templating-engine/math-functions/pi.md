---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: pi
---

# pi

Returns the value of pi.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 3.141592653589793",
    "test": "{{"{{pi()"}}}}"
  }
}
```
