---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: findFirst
---

# findFirst

Finds the first element in the given array that matches the given predicate
## Arguments

- `array` - The array to find in
- `predicate(element, index)` - (optional) The predicate to match by

## Example

```json
{
  "$template": {
	"$comment": "The field below will be 8",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].findFirst(x => x >= 5)"}}}}"
  }
}
```
