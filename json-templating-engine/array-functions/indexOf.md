---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: indexOf
---

# indexOf

Returns the first index of the given value in the given array
## Arguments

- `array` - The array to check
- `value` - The value to check for

## Example

```json
{
  "$template": {
	"$comment": "The field below will be 3",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].indexOf(5)"}}}}"
  }
}
```
