---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: hash
---

# hash

Returns an integer hash of the string. Note that 32 bit size does not guarantee, the generated hash will always be unique.

## Arguments

 - string: Text to hash

## Example

```json
{
  "$template": {
    "$comment": "The field below will be -1238115836",
    "test": "{{"{{hash('this_is_a_test'))}}"}}"
  }
}
```
