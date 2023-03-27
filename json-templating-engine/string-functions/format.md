---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: format
---

# format

Formats a string using the given arguments.
## Arguments

- `string` - The string to format.
- `args...` - The arguments to use when formatting the string.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 1.0",
    "test": "{{"{{=formatString('%s %s', 'hello', 'world')"}}}}"
  }
}
```
