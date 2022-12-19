---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: random
---

# random

Returns a random number between 0 and 1.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be a random number between 0 and 1",
    "test": "{{"{{random()"}}}}"
  }
}
```
