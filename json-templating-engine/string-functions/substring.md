---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: substring
---

# substring

Returns a string that is a substring of this string. The substring begins at the specified beginIndex and extends to the character at index endIndex - 1 or to the end of the string, if none specified.

## Arguments

 - string: Text to transform
 - beginIndex: the beginning index, inclusive
 - endIndex: (optional) the ending index, exclusive

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 45",
    "test": "{{"{{substring('123456789', 3, 5))}}"}}"
  }
}
```
