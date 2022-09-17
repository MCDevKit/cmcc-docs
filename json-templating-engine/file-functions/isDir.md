---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: isDir
---

# isDir

Checks if the given path is a directory.
## Arguments

- `path` - The path to the file.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true if the path is a directory",
    "test": "{{"{{isDir('data')"}}}}"
  }
}
```
