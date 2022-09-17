---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: fileList
---

# fileList

Lists all files in a directory.
## Arguments

- `path` - The path to the directory to list.
- `filter` - (optional) A glob filter to match files against.

## Example

{
  "$template": {
    "$comment": "The field below will be an array of all files with .json extension in the data directory",
    "test": "{{"{{fileList('data', "*.json")"}}}}"
  }
}
