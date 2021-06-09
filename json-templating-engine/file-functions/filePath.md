---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: filePath
---

# filePath

Returns a directory path from file path in first argument.

## Arguments

 - path: A path to the file

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'resources/textures/particle/'",
    "test": "{{"{{filePath('resources/textures/particle/particles.png')}}"}}"
  }
}
```
