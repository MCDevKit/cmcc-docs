---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: load
---

# load

Loads a JSON file from the given path.

**This method is marked as unsafe. It can be disabled in certain environments.**
## Arguments

- `path` - The path to the file to load.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be an object from the file data.json",
    "test": "{{"{{load('data.json')"}}}}"
  }
}
```
