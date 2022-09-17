---
layout: page
grand_parent: JSON Templating Engine
parent: String functions
title: join
---

# join

Joins an array of strings together into a single string, separated by a separator.
## Arguments

- `strings` - The array of strings to join together.
- `separator` - The separator to use.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be 'this,is,a,test'",
    "test": "{{"{{join(['this', 'is', 'a', 'test'], ',')"}}}}"
  }
}
```
