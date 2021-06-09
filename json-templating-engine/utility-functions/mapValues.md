---
layout: page
grand_parent: JSON Templating Engine
parent: Utility functions
title: mapValues (deprecated)
---

# mapValues (deprecated)

Returns an array, where each element is replaced with the value from the specified map.

## Arguments

 - array: Array to be mapped
 - map: Map object

## Example

Given scope
```json
{
  "map": {
    "1": "someVal",
    "2": "anotherVal"
  },
  "testArray": ["1", "2"]
}
```
for query
```json
{
  "$template": {
    "test": "{{"{{mapValues(testArray, map)}}"}}"
  }
}
```

the result will be
```json
[
  "someVal",
  "anotherVal"
]
```
