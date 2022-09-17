---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: filter
---

# filter

Filters the elements in the given array based on the given predicate
## Arguments

- `array` - The array to filter
- `predicate(element, index)` - The predicate to filter by

## Example

```json
{
  "$template": {
	"$comment": "The field below will be [5, 8, 10]",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].filter(x => x >= 5)"}}}}"
  }
}
```
