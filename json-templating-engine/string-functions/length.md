---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: length
---

# length

Returns the length of this string.

## Arguments

 - string: String

## Example

```json
{
  "$template": {
    "$comment": "The field below will be ['h', 'e', 'l', 'l', 'o']",
    "test": "{{"{{chars('hello')"}}}}"
  }
}
```
