---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: replace
---

# replace

Replaces all occurrences of a substring within a string with another string.
## Arguments

- `string` - The string to search.
- `old` - The substring to replace.
- `new` - The string to replace with.

## Example

{
  "$template": {
    "$comment": "The field below will be 'this_is_a_test'",
    "test": "{{"{{replace('this is a test', ' ', '_')"}}}}"
  }
}
