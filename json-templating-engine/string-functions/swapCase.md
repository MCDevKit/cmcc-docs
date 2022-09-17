---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: swapCase
---

# swapCase

Swaps the case of each letter in a string.
## Arguments

- `string` - The string to swap the case of.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'tHIS IS A TEST'",
    "test": "{{"{{swapCase('This is a test')"}}}}"
  }
}
```
