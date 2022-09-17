---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: reverse
---

# reverse

Reverses the given array
## Arguments

- `array` - The array to reverse

## Example

```json
{
  "$template": {
	"$comment": "The field below will be [10, 8, 5, 3, 2, 1]",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].reverse()"}}}}"
  }
}
```
