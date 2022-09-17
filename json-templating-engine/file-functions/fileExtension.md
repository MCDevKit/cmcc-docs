---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: fileExtension
---

# fileExtension

Gets the extension of a file.
## Arguments

- `path` - The path to the file.

## Example

{
  "$template": {
    "$comment": "The field below will be '.json'",
    "test": "{{"{{fileExtension('data.json')"}}}}"
  }
}
