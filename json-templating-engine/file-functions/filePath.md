---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: filePath
---

# filePath

Gets the path of a file.
## Arguments

- `path` - The path to the file.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'data'",
    "test": "{{"{{filePath('data.json')"}}}}"
  }
}
```
