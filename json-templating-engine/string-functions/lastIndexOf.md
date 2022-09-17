---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: lastIndexOf
---

# lastIndexOf

Returns the index of the last occurrence of a substring within a string.
## Arguments

- `string` - The string to search.
- `substring` - The substring to search for.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 8",
    "test": "{{"{{lastIndexOf('this is a test', 'test')"}}}}"
  }
}
```
