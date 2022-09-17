---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: load
---

# load

Loads a JSON file from the given path.
## Arguments

- `path` - The path to the file to load.

## Example

{
  "$template": {
    "$comment": "The field below will be an object from the file data.json",
    "test": "{{"{{load('data.json')"}}}}"
  }
}
