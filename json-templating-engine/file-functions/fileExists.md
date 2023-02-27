---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: fileExists
---

# fileExists

Checks if the file under given path exists.

**This method is marked as unsafe. It can be disabled in certain environments.**
## Arguments

- `path` - The path to the file.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true if the file test.txt exists",
    "test": "{{"{{fileExists('test.txt')"}}}}"
  }
}
```
