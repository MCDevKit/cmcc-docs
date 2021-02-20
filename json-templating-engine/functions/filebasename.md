---
layout: page
grand_parent: JSON Templating Engine
parent: Functions
title: fileBaseName
---

# fileBaseName

`fileBaseName` is a function, that returns a name from file path in first argument.

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