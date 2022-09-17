---
layout: page
grand_parent: JSON Templating Engine
parent: Array functions
title: keys
---

# keys

Returns an array of the keys of the given object
## Arguments

- `object` - The object to get the keys from

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
    "test": "{{"{{keys(testObject)"}}}}"
  }
}
```
the result will be
```json
[
  "test1", "test2"
]
```
