---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: sublist
---

# sublist

Returns a sublist of the given array
## Arguments

- `array` - The array to slice
- `start` - The start index
- `end` - (optional) The end index

## Example

```json
{
  "$template": {
	"$comment": "The field below will be [1, 2, 3]",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].sublist(0, 3)"}}}}"
  }
}
```
