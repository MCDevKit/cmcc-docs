---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: title
---

# title

Capitalizes the first letter of each word in a string.
## Arguments

- `string` - The string to capitalize.

## Example

{
  "$template": {
    "$comment": "The field below will be 'This Is A Test'",
    "test": "{{"{{title('this is a test')"}}}}"
  }
}
