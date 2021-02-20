---
layout: page
grand_parent: JSON Templating Engine
parent: Functions
title: fileList
---

# fileList

`fileList` is a function, that returns an array of file names.

## Arguments

 - path: A path to the folder
 - filter: (optional) A wildcard filter for filtering the file list

## Example

```json
{
  "$template": {
    "{{#fileList('resources/textures/particle', '*.png')": {
      "{{index}}": "{{value}}"
    }
  }
}
```