---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: toUpperCase
---

# toUpperCase

Converts a string to uppercase.
## Arguments

- `string` - The string to convert.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'THIS IS A TEST'",
    "test": "{{"{{toUpperCase('this is a test')"}}}}"
  }
}
```
