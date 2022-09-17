---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: min
---

# min

Finds the minimum value in the given array
## Arguments

- `array` - The array to find the minimum value in
- `selector(element, index)` - (optional) The selector to apply to each element before finding the minimum value

## Example

```json
{
  "$template": {
	"$comment": "The field below will be 1",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].min()"}}}}"
  }
}
```
