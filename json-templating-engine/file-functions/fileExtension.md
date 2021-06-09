---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: fileExtension
---

# fileExtension

Returns an extension from file path in first argument.

## Arguments

 - path: A path to the file

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'png'",
    "test": "{{"{{fileExtension('resources/textures/particle/particles.png')}}"}}"
  }
}
```
