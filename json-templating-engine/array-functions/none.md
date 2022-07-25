---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: none
---

# none

Returns whether no elements of the supplied array match the provided predicate.

## Arguments

 - array: Array to check
 - predicate: Predicate to apply to elements of this stream

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{['asd', '123', 123, 9].none(x => x == '999')"}}}}"
  }
}
```
