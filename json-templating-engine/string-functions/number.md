---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: number
---

# number

Converts a string to a number.
## Arguments

- `string` - The string to convert.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 1.0",
    "test": "{{"{{=number('1.0')"}}}}"
  }
}
```
