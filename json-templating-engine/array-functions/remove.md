---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: remove
---

# remove

Removes the element at the given index from the given array
## Arguments

- `array` - The array to remove from
- `index` - The index to remove or a predicate to find the elements to remove

## Example

```json
{
  "$template": {
	"$comment": "The field below will be [1, 3, 5, 8, 10]",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].remove(1)"}}}}"
  }
}
```
