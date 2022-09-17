---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: reduce
---

# reduce

Reduces the given array to a single value using the given accumulator function
## Arguments

- `array` - The array to reduce
- `accumulator(accumulator, element, index)` - The accumulator function
- `initialValue` - (optional) The initial value for the accumulator

## Example

```json
{
  "$template": {
	"$comment": "The field below will be 29",
	"test": "{{"{{[1, 2, 3, 5, 8, 10].reduce((a, b) => a + b)"}}}}"
  }
}
```
