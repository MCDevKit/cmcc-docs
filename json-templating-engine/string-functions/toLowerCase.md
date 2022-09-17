---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: toLowerCase
---

# toLowerCase

Converts a string to lowercase.
## Arguments

- `string` - The string to convert.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'this is a test'",
    "test": "{{"{{toLowerCase('THIS IS A TEST')"}}}}"
  }
}
```
