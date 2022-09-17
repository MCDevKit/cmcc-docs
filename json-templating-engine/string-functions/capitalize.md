---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: capitalize
---

# capitalize

Capitalizes the first letter of a string.
## Arguments

- `string` - The string to capitalize.

## Example

{
  "$template": {
    "$comment": "The field below will be 'This is a test'",
    "test": "{{"{{capitalize('this is a test')"}}}}"
  }
}
