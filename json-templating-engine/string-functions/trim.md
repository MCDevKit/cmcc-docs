---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: trim
---

# trim

Removes leading and trailing whitespace from a string.
## Arguments

- `string` - The string to trim.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'this is a test'",
    "test": "{{"{{trim('  this is a test  ')"}}}}"
  }
}
```
