---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: removeFront
---

# removeFront

Removes and returns the first element from the given array
## Arguments

- `array` - The array to remove from

## Example

```json
{
  "$template": {
	"$comment": "The field below will be 1",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].removeFront()"}}}}"
  }
}
```
