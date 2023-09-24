---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: prepend
---

# prepend

Adds the given value to the start of the given array
## Arguments

- `array` - The array to add to
- `element...` - The elements to add

## Example

```json
{
  "$template": {
	"$comment": "The field below will be [-2, 1, 2, 3, 5, 8, 10]",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].prepend(-2)"}}}}"
  }
}
```
