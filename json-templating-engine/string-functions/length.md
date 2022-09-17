---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: length
---

# length

Returns the length of a string.
## Arguments

- `string` - The string to get the length of.

## Example

{
  "$template": {
    "$comment": "The field below will be 4",
    "test": "{{"{{length('this')"}}}}"
  }
}
