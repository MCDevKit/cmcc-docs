---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: load
---

# load

Returns json file as an object.

## Arguments

 - path: A path to the file

## Example

```json
{
  "$template": {
    "$comment": "The field below will be an object from the file data.json",
    "test": "{{"{{load('data.json')"}}}}"
  }
}
```
