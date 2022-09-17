---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: findLast
---

# findLast

Finds the last element in the array that matches the given predicate
## Arguments

- `array` - The array to search
- `predicate(element, index)` - (optional) The predicate to test each element against

## Example

```json
{
  "$template": {
	"$comment": "The field below will be 10",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].findLast(e => e % 2 == 0)"}}}}"
  }
}
```
