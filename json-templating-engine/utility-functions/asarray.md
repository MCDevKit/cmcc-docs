---
layout: page
grand_parent: JSON Templating Engine
parent: Utility functions
title: asArray
---

# asArray

Returns an array of objects from an object, where each object in resulting array has fields with field name and value.

## Arguments

 - object: Object to be mapped
 - keyName: Name of the key field
 - valueName: Name of the value field

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
    "test": "{{"{{asArray(testObject, 'key', 'value'"}})}}"
  }
}
```

the result will be
```json
[
  {
    "key": "test1"
    "value": "someVal"
  },
  {
    "key": "test2"
    "value": "anotherVal"
  }
]
```