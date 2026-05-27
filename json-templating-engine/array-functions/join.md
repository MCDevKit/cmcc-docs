---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: join
---

# join

Joins the elements of the array into a string with no separator
## Arguments

- `array` - The array to join

## Example

```json
{
  "$template": {
	"$comment": "The field below will be \"123\"",
	"test": "{{"{{[1, 2, 3].join()"}}}}"
  }
}
```
