---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: split
---

# split

Returns an array from string.

## Arguments

 - string: Text to split
 - delimiter: Text to split by

## Example

```json
{
  "$template": {
    "$comment": "The field below will be ['this', 'is', 'a', 'test']",
    "test": "{{"{{split('this_is_a_test', '_')"}}}}"
  }
}
```
