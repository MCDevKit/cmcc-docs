---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: loadText
---

# loadText

Loads a text file from the given path.

**This method is marked as unsafe. It can be disabled in certain environments.**
## Arguments

- `path` - The path to the file to load.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be a string from the file test.molang",
    "test": "{{"{{loadText('test.molang')"}}}}"
  }
}
```
