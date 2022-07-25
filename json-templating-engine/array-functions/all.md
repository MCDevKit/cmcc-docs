---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: all
---

# all

Returns whether all elements of the supplied array match the provided predicate.

## Arguments

 - array: Array to check
 - predicate: Predicate to apply to elements of this stream

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{['asd', '123'].all(x => x.length() == 3)"}}}}"
  }
}
```
