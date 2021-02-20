---
layout: page
grand_parent: JSON Templating Engine
parent: Functions
title: imageHeight
---

# imageHeight

`imageHeight` is a function, that returns an image height from file path in first argument.

## Arguments

 - path: A path to the image

## Example

```json
{
  "$template": {
    "test": "{{"{{imageHeight('resources/textures/particle/particles.png')"}}}}"
  }
}
```