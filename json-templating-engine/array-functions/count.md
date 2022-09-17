---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: count
---

# count

Counts the number of elements in the given array that match the given predicate
## Arguments

- `array` - The array to check
- `predicate(element, index)` - (optional) The predicate to filter by

## Example

```json
{
  "$template": {
	"$comment": "The field below will be 3",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].count(x => x >= 5)"}}}}"
  }
}
```
