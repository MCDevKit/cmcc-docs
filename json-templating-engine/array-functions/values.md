---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: values
---

# values

Returns an array of the values of the given object
## Arguments

- `object` - The object to get the values from

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
    "test": "{{"{{values(testObject)"}}}}"
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
