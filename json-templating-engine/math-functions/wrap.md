---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: wrap
---

# wrap

Returns the given number wrapped between the first and second argument.
## Arguments

- `value` - The value to wrap.
- `start` - (optional) The start of the range to wrap the value between.
- `end` - The end of the range to wrap the value between.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 1",
    "test": "{{"{{wrap(10, 0, 4)"}}}}"
  }
}
```
