---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: encode
---

# encode

Returns a number with numbers encoded in given bit space.


## Arguments

 - array: Source array
 - space: Bit space for the values. Must be power of 2.
 - predicate(element, index): Lambda, that should return an integer number to encode

## Example

```json
{
  "$template": {
    "$comment": "The field below will be -2023406815 (1000 0111 0110 0101 0100 0011 0010 0001)",
    "test": "{{"{{(1..10).encode(16, x => x)"}}}}"
  }
}
```
