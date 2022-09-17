---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: startsWith
---

# startsWith

Returns true if a string starts with a substring.
## Arguments

- `string` - The string to search.
- `substring` - The substring to search for.

## Example

{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{startsWith('this is a test', 'this')"}}}}"
  }
}
