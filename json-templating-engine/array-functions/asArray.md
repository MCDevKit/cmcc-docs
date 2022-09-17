---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: asArray
---

# asArray

Converts an object to an array of objects with the given key and value
## Arguments

- `object` - The object to convert
- `key` - The key to use for the new objects
- `value` - The value to use for the new objects

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
    "test": "{{"{{asArray(testObject, 'key', 'value')"}}}}"
  }
}
```
the result will be
```json
[
  {
    "key": "test1",
    "value": "someVal"
  },
  {
    "key": "test2",
    "value": "anotherVal"
  }
]
```
