---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: random
---

# random

Finds the random element in the array
## Arguments

- `array` - The array to get random element from

## Example

```json
{
  "$template": {
	"$comment": "The field below will be a randomly selected element from the array",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].random()"}}}}"
  }
}
```
