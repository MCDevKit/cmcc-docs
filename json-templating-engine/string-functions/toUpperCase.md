---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: toUpperCase
---

# toUpperCase

Returns a string, where all letters are uppercase.

## Arguments

 - string: Text to transform

## Example

```json
{
  "$template": {
    "$comment": "The field below will be TEST",
    "test": "{{"{{toUpperCase('Test'))}}"}}"
  }
}
```
