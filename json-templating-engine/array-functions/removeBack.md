---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: removeBack
---

# removeBack

Removes and returns the last element from the given array
## Arguments

- `array` - The array to remove from

## Example

```json
{
  "$template": {
	"$comment": "The field below will be 10",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].removeBack()"}}}}"
  }
}
```
