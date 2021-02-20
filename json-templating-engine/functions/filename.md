---
layout: page
grand_parent: JSON Templating Engine
parent: Functions
title: fileName
---

# fileName

`fileName` is a function, that returns a name and extension from file path in first argument.

## Arguments

 - path: A path to the file

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'particles.png'",
    "test": "{{"{{fileName('resources/textures/particle/particles.png'"}})}}"
  }
}
```