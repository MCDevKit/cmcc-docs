---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: sublist
---

# sublist

Returns a portion of the array between the specified startIndex, inclusive, and endIndex, exclusive. (If startIndex and endIndex are equal, the returned array is empty.)


## Arguments

 - array: Source array
 - startIndex: Starting index (inclusive) of the sub list
 - endIndex: Ending index (exclusive) of the sub list. If none provided, will use the end of the array

## Example

```json
{
  "$template": {
    "$comment": "The field below will be [4, 5, 6, 7]",
    "test": "{{"{{0..10.sublist(4, 8)"}}}}"
  }
}
```
