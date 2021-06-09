---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: keys
---

# keys

Returns an array of keys from the object.

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
    "test": "{{"{{keys(testObject)}}"}}"
  }
}
```
the result will be
```json
[
  "test1", "test2"
]
```
