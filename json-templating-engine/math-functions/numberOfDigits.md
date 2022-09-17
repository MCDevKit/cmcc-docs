---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: numberOfDigits
---

# numberOfDigits

Returns the number of digits in the given number.
## Arguments

- `number` - The number to count the number of digits.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 3",
    "test": "{{"{{numberOfDigits(123)"}}}}"
  }
}
```
