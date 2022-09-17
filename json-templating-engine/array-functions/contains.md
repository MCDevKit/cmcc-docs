---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: contains
---

# contains

Checks if the given array contains the given value
## Arguments

- `array` - The array to check
- `value` - The value to check for

## Example

```json
{
  "$template": {
	"$comment": "The field below will be true",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].contains(5)"}}}}"
  }
}
```
