---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: map
---

# map

Maps the elements in the given array based on the given selector
## Arguments

- `array` - The array to map
- `selector(element, index)` - The selector to apply to each element

## Example

```json
{
  "$template": {
	"$comment": "The field below will be [2, 4, 6, 10, 16, 20]",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].map(x => x * 2)"}}}}"
  }
}
```
