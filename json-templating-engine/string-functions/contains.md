---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: contains
---

# contains

Checks if a string contains a substring.
## Arguments

- `string` - The string to search.
- `substring` - The substring to search for.

## Example

{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{contains('this is a test', 'test')"}}}}"
  }
}
