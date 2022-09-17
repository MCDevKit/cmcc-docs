---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: chars
---

# chars

Returns the characters of a string as an array.
## Arguments

- `string` - The string to split into characters.

## Example

{
  "$template": {
    "$comment": "The field below will be ['t', 'h', 'i', 's']",
    "test": "{{"{{chars('this')"}}}}"
  }
}
