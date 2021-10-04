---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: regexReplace
---

# regexReplace

Replaces each substring of this string that matches the given regular expression with the given replacement.

## Arguments

 - string: Text to transform
 - string: Regular expression
 - string: Replacement

## Example

```json
{
  "$template": {
    "$comment": "The field below will be player.first_person",
    "test": "{{"{{regexReplace('controller.animation.player.first_person', '(?:controller\.)?(?:animation\.)(.+)', '$1'))"}}}}"
  }
}
```
