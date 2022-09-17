---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: encode
---

# encode

Encodes the given array of numbers to a single number in a bit width calculated with the given maximum
## Arguments

- `array` - The array to encode
- `maximum` - The maximum value in the array. Must be power of 2.
- `selector(element, index)` - (optional) The selector to apply to each element before encoding

## Example

```json
{
  "$template": {
	"$comment": "The field below will be -2023406815 (1000 0111 0110 0101 0100 0011 0010 0001)",
	"test": "{{"{{(1..10).encode(16)"}}}}"
  }
}
```
