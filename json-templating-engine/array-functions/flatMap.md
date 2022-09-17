---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: flatMap
---

# flatMap

Maps the elements in the given array based on the given selector, then flattens the result
## Arguments

- `array` - The array to map
- `selector(element, index)` - (optional) The selector to apply to each element

## Example

```json
{
  "$template": {
	"$comment": "The field below will be [1, 2, 2, 4, 3, 6, 5, 10, 8, 16, 10, 20]",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].flatMap(x => [x, x * 2])"}}}}"
  }
}
```
