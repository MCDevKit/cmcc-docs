---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: endsWith
---

# endsWith

Returns true if a string ends with a substring.
## Arguments

- `string` - The string to search.
- `substring` - The substring to search for.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{endsWith('this is a test', 'test')"}}}}"
  }
}
```
