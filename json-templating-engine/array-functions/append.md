---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: append
---

# append

Adds the given value to the end of the given array
## Arguments

- `array` - The array to add to
- `element...` - The elements to add

## Example

```json
{
  "$template": {
	"$comment": "The field below will be [1, 2, 3, 5, 8, 10, 12]",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].append(12)"}}}}"
  }
}
```
