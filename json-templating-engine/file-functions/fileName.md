---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: fileName
---

# fileName

Gets the name of a file.
## Arguments

- `path` - The path to the file.

## Example

{
  "$template": {
    "$comment": "The field below will be the name of the file data.json",
    "test": "{{"{{fileName('dir/data.json')"}}}}"
  }
}
