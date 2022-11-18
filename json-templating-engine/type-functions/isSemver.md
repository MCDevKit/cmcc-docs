---
layout: page
grand_parent: JSON Templating Engine
parent: Type functions
title: isSemver
---

# isSemver

Returns whether the argument is a semantic version object.
## Arguments

- `object` - The value to check.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be true",
    "test": "{{"{{isSemver(semver('1.10.0'))"}}}}"
  }
}
```
