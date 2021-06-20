---
layout: page
grand_parent: JSON Templating Engine
parent: Utility functions
title: exists
---

# exists

Returns whether the object has specified field.

## Arguments

 - object: Object to check
 - field name: Field name

## Example

Scope
```json
{
  "map": {
    "1": "someVal",
    "2": "anotherVal"
  }
}
```

```json
{
  "$template": {
    "$comment": "The field below will be false",
    "test": "{{"{{exists(map, '3')"}}}}"
  }
}
```
