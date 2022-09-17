---
layout: page
grand_parent: JSON Templating Engine
parent: Image functions
title: imageWidth
---

# imageWidth

Gets the width of an image.
## Arguments

- `path` - The path to the image file.

## Example

{
  "$template": {
    "test": "{{"{{imageWidth('resources/textures/particle/particles.png')"}}}}"
  }
}
