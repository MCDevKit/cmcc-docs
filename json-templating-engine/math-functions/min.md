---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: min
---

# min

Returns the smallest of the given numbers.
## Arguments

- `number1` - The first number to compare.
- `number2` - The second number to compare.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 3",
    "test": "{{"{{min(3, 5)"}}}}"
  }
}
```
