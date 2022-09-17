---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: fileBaseName
---

# fileBaseName

Gets the base name of a file.
## Arguments

- `path` - The path to the file.

## Example

{
  "$template": {
    "$comment": "The field below will be 'data'",
    "test": "{{"{{fileBaseName('data.json')"}}}}"
  }
}
