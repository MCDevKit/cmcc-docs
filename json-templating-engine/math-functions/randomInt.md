---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: randomInt
---

# randomInt

Returns a random integer number between the first and second argument.
## Arguments

- `min` - The minimum value of the random number.
- `max` - The maximum value of the random number.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be a random number between 0 and 1",
    "test": "{{"{{random()"}}}}"
  }
}
```
