---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: replace
---

# replace

Returns string from the first argument with occurrences of the second argument replaced by third argument.

## Arguments

 - original string: String to be modified
 - target: String to be replaced
 - replacement: Replacement string

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'this_is_a_test'",
    "test": "{{"{{replace('this is a test', ' ', '_')"}}}}"
  }
}
```
