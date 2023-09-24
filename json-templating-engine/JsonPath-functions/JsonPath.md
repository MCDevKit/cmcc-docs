---
layout: page
grand_parent: JSON Templating Engine
parent: JsonPath functions
title: JsonPath
---

# JsonPath

Creates a new JsonPath object from a string.
## Arguments

- `path` - The path to parse.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be '#/test/path[1]'",
    "test": "{{"{{JsonPath('#/test/path[1]')"}}}}"
  }
}
```
