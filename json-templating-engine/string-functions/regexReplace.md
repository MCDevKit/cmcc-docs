---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: regexReplace
---

# regexReplace

Replaces the first occurrence of a substring that matches a regular expression.
## Arguments

- `string` - The string to search.
- `regex` - The regular expression to search for.
- `replacement` - The string to replace the substring with.

## Example

{
  "$template": {
    "$comment": "The field below will be 'this-is-a-test'",
    "test": "{{"{{regexReplace('this is a test', '\s', '-')}"
  }
}
