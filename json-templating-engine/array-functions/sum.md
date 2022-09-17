---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: sum
---

# sum

Sums the elements in the given array
## Arguments

- `array` - The array to sum
- `selector(element, index)` - (optional) The selector to apply to each element before summing

## Example

```json
{
  "$template": {
	"$comment": "The field below will be 31",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].sum(x => x)"}}}}"
  }
}
```
