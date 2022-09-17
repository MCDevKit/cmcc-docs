---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: max
---

# max

Returns the largest of the given numbers.
## Arguments

- `number1` - The first number to compare.
- `number2` - The second number to compare.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 5",
    "test": "{{"{{max(3, 5)"}}}}"
  }
}
```
