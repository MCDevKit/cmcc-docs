---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: indexOf
---

# indexOf

Returns an index of second string inside the firs string or -1 if not found.

## Arguments

 - string: Text to search inside
 - string to search: Text to search

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 4",
    "test": "{{"{{indexOf('this_is_a_test', '_is_'"}})}}"
  }
}
```