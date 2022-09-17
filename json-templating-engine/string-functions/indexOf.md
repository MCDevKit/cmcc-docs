---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: indexOf
---

# indexOf

Returns the index of the first occurrence of a substring within a string.
## Arguments

- `string` - The string to search.
- `substring` - The substring to search for.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 8",
    "test": "{{"{{indexOf('this is a test', 'test')"}}}}"
  }
}
```
