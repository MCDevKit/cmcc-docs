---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: isDir
---

# isDir

Returns whether a file is a directory.

**This method is marked as unsafe. It can be disabled by certain environments.**

## Arguments

 - path: A path to the file

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{isDir('resources/textures/particle/')"}}}}"
  }
}
```
