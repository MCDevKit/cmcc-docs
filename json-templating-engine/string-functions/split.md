---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: split
---

# split

Splits a string into an array of strings, using a separator.
## Arguments

- `string` - The string to split.
- `separator` - The separator to use.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be ['this', 'is', 'a', 'test']",
    "test": "{{"{{split('this is a test', ' ')"}}}}"
  }
}
```
