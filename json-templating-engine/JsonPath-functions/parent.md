---
layout: page
grand_parent: JSON Templating Engine
parent: JsonPath functions
title: parent
---

# parent

Returns the parent of the given path.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be '#/test/path'",
    "test": "{{"{{JsonPath('#/test/path[1]').parent()"}}}}"
  }
}
```
