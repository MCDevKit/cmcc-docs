---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: startsWith
---

# startsWith

Tests if this string starts with the specified prefix.

## Arguments

 - string: Text to check
 - string: Prefix

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{startsWith('testing', 'test'))"}}}}"
  }
}
```
