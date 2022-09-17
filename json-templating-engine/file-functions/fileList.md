---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: fileList
---

# fileList

Lists all files in a directory.

**This method is marked as unsafe. It can be disabled in certain environments.**
## Arguments

- `path` - The path to the directory to list.
- `filter` - (optional) A glob filter to match files against.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be an array of all files with .json extension in the data directory",
    "test": "{{"{{fileList('data', "*.json")"}}}}"
  }
}
```
