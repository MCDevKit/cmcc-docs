---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: fileBaseName
---

# fileBaseName

Returns a name from file path in first argument.

## Arguments

 - path: A path to the file

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'particles'",
    "test": "{{"{{fileBaseName('resources/textures/particle/particles.png')"}}}}"
  }
}
```
