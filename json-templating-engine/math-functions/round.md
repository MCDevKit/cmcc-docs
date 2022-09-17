---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: round
---

# round

Returns the nearest integer to the given number.
## Arguments

- `number` - The number to round.
- `precision` - (optional) The number of decimal places to round to.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 3.142",
    "test": "{{"{{round(3.1415, 3)"}}}}"
  }
}
```
