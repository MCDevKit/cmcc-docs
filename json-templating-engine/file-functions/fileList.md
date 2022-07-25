---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: fileList
---

# fileList

Returns an array of file names.

**This method is marked as unsafe. It can be disabled by certain environments.**

## Arguments

 - path: A path to the folder
 - filter: (optional) A wildcard filter for filtering the file list

## Example

```json
{
  "$template": {
    "{{"{{#fileList('resources/textures/particle', '*.png')"}}}}": {
      "{{"{{index"}}}}": "{{"{{value"}}}}"
    }
  }
}
```
