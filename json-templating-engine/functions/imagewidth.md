---
layout: page
grand_parent: JSON Templating Engine
parent: Functions
title: imageWidth
---

# imageWidth

`imageWidth` is a function, that returns an image width from file path in first argument.

## Arguments

 - path: A path to the image

## Example

```json
{
  "$template": {
    "test": "{{"{{imageWidth('resources/textures/particle/particles.png')"}}}}"
  }
}
```