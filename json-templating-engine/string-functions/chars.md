---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: chars
---

# chars

Returns an array of strings, where each string is another character.

## Arguments

 - string: Text convert

## Example

```json
{
  "$template": {
    "$comment": "The field below will be ['h', 'e', 'l', 'l', 'o']",
    "test": "{{"{{chars('hello')"}}}}"
  }
}
```
