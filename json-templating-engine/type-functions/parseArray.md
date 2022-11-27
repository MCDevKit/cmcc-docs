---
layout: page
grand_parent: JSON Templating Engine
parent: Type functions
title: parseArray
---

# parseArray

Returns the JSON string in the argument as an array.
## Arguments

- `string` - The JSON string to parse.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [1, 2, 3]",
    "test": "{{"{{parseArray('[1, 2, 3]')"}}}}"
  }
}
```
