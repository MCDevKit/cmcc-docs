---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: endsWith
---

# endsWith

Tests if this string ends with the specified suffix.

## Arguments

 - string: Text to check
 - string: Suffix

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{endsWith('testing', 'ing'))"}}}}"
  }
}
```
