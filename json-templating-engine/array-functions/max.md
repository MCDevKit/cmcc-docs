---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: max
---

# max

Finds the maximum value in the given array
## Arguments

- `array` - The array to find the maximum value in
- `selector(element, index)` - (optional) The selector to apply to each element before finding the maximum value

## Example

```json
{
  "$template": {
	"$comment": "The field below will be 10",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].max()"}}}}"
  }
}
```
