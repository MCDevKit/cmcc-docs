---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: capitalize
---

# capitalize

Returns a string, where all letters are lowercase, and the first letter is uppercase.

## Arguments

 - string: Text to transform

## Example

```json
{
  "$template": {
    "$comment": "The field below will be Test",
    "test": "{{"{{capitalize('test'))}}"}}"
  }
}
```
