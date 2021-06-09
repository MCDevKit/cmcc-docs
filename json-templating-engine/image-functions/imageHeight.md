---
layout: page
grand_parent: JSON Templating Engine
parent: Image functions
title: imageHeight
---

# imageHeight

Returns an image height from file path in first argument.

## Arguments

 - path: A path to the image

## Example

```json
{
  "$template": {
    "test": "{{"{{imageWidth('resources/textures/particle/particles.png')}}"}}"
  }
}
```
