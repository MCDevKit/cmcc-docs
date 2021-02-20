---
layout: page
grand_parent: JSON Templating Engine
parent: Functions
title: fileExtension
---

# fileExtension

`fileExtension` is a function, that returns an extension from file path in first argument.

## Arguments

 - path: A path to the file

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'png'",
    "test": "{{"{{fileExtension('resources/textures/particle/particles.png')"}}}}"
  }
}
```