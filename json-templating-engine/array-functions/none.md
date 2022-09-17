---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: none
---

# none

Checks if none of the elements in the given array match the given predicate
## Arguments

- `array` - The array to check
- `predicate(element, index)` - The predicate to check against

## Example

```json
{
  "$template": {
	"$comment": "The field below will be false",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].none(x => x > 5)"}}}}"
  }
}
```
