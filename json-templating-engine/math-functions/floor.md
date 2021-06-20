---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: floor
---

# floor

Returns an integer number rounded down.

## Arguments

 - number: A number to floor

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 3",
    "test": "{{"{{floor(3.6)"}}}}"
  }
}
```
