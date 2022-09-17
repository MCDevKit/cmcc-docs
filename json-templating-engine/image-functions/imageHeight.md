---
layout: page
grand_parent: JSON Templating Engine
parent: Image functions
title: imageHeight
---

# imageHeight

Gets the height of an image.
## Arguments

- `path` - The path to the image file.

## Example

{
  "$template": {
    "test": "{{"{{imageHeight('resources/textures/particle/particles.png')"}}}}"
  }
}
