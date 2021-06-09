---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: join
---

# join

Joins all values in a given array and returns as a string.

## Arguments

 - values to join: Array of values to join
 - delimiter: String inserted in between the values

## Example

```json
{
  "$template": {
    "$comment": "For an array ['this', 'is', 'a', 'test'] the field below will be 'this_is_a_test'",
    "test": "{{"{{join(arr, '_')}}"}}"
  }
}
```
