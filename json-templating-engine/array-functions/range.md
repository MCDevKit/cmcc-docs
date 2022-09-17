---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: range
---

# range

Creates an array of indices from the given array
## Arguments

- `array` - The array to create indices for

## Example

```json
{
  "$template": {
	"$comment": "The field below will be [0, 1, 2, 3, 4, 5]",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].range()"}}}}"
  }
}
```
