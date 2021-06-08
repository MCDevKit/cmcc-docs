---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: contains
---

# contains

Returns whether supplied array contains provided value.

## Arguments

 - array: Array to check
 - value: Value to search for (currently a string, or a number only)

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{contains(['asd', '123', 123, 9], '123')"}})}}"
  }
}
```