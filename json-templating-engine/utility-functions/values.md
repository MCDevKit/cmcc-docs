---
layout: page
grand_parent: JSON Templating Engine
parent: Utility functions
title: values
---

# values

Returns an array of values from an object.

## Arguments

 - object: Source object

## Example

Given scope
```json
{
  "testObject": {
    "test1": "someVal",
    "test2": "anotherVal"
  }
}
```
for query
```json
{
  "$template": {
    "test": "{{"{{values(testObject"}})}}"
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