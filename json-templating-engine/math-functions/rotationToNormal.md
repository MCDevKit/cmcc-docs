---
layout: page
grand_parent: JSON Templating Engine
parent: Math functions
title: rotationToNormal
---

# rotationToNormal

Returns normal (direction) vector based on pitch and yaw rotation.

## Arguments

 - pitch: A pitch rotation (rotation in x-axis)
 - yaw: A yaw rotation (rotation in y-axis)

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [0,0,1]",
    "test": "{{"{{rotationToNormal(0, 0)"}}}}"
  }
}
```
