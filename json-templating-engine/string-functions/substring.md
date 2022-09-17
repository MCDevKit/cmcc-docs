---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: substring
---

# substring

Returns a substring of a string.
## Arguments

- `string` - The string to get the substring from.
- `start` - The starting index of the substring.
- `end` - (optional) The ending index of the substring.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'this'",
    "test": "{{"{{substring('this is a test', 0, 4)"}}}}"
  }
}
```
