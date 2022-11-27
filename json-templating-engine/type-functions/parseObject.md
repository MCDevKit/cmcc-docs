---
layout: page
grand_parent: JSON Templating Engine
parent: Type functions
title: parseObject
---

# parseObject

Returns the JSON string in the argument as an object.
## Arguments

- `string` - The JSON string to parse.

## Example

```json
{
  "$scope": {
	"test": "{\"a\": 1, \"b\": 2}"
  },
  "$template": {
    "$comment": "The field below will be 1",
    "test": "{{"{{parseObject(test).a"}}}}"
  }
}
```
