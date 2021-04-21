---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: toUpperCase
---

# toLowerCase

Returns a string, where all letters are lowercase.

## Arguments

 - string: Text to transform

## Example

```json
{
  "$template": {
    "$comment": "The field below will be test",
    "test": "{{"{{toLowerCase('Test')"}})}}"
  }
}
```