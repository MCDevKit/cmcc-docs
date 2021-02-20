---
layout: page
grand_parent: JSON Templating Engine
parent: Functions
title: fileListRecurse
---

# fileListRecurse

`fileListRecurse` is a function, that returns an array of file paths recursively, which means, that if the folder contains another folder, its contents will also be added to the array.

## Arguments

- path: A path to the folder
- filter: (optional) A wildcard filter for filtering the file list

## Example

```json
{
  "$template": {
    "{{"{{#fileListRecurse('resources/textures', '*.png')"}}}}": {
      "{{"{{index"}}}}": "{{"{{value"}}}}"
    }
  }
}
```