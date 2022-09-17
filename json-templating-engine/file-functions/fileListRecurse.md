---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: fileListRecurse
---

# fileListRecurse

Lists all files in a directory, recursively.
## Arguments

- `path` - The path to the directory to list.
- `filter` - (optional) A glob filter to match files against.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be an array of all files with .json extension in the data directory and its subdirectories",
    "test": "{{"{{fileListRecurse('data', "*.json")"}}}}"
  }
}
```
