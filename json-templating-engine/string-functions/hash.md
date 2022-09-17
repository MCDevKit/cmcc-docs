---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: hash
---

# hash

Returns an integer hash of a string.
## Arguments

- `string` - The string to hash.

## Example

{
  "$template": {
    "$comment": "The field below will be 2139996864",
    "test": "{{"{{hash('this is a test')"}}}}"
  }
}
