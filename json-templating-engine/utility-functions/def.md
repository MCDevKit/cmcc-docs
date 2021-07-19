---
layout: page
grand_parent: JSON Templating Engine
parent: Utility functions
title: def
---

# def

Returns the specified field value or default if doesn't exist or null.

## Arguments

 - object: Object to check
 - field name: Field name
 - default value: Value returned if the field doesn't exist or null

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
    "$comment": "The field below will be 'defaultVal'",
    "test": "{{"{{def(map, '3', 'defaultVal')"}}}}"
  }
}
```
