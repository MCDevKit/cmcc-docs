---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: contains
---

# contains

Returns whether first string argument contains second string argument.

## Arguments

 - string: Text, on which the search is executed
 - string to search: Text to search

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{contains('this_is_a_test', '_')"}}}}"
  }
}
```
