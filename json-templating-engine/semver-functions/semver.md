---
layout: page
grand_parent: JSON Templating Engine
parent: Semver functions
title: semver
---

# semver

Converts a string semver to semver object.
## Arguments

- `version` - The semver string or array to parse. Optionally the major, minor and patch can be specified as separate arguments.

## Example

```json
{
  "$template": {
    "$comment": "The field below will be '1.8.0'",
    "test": "{{"{{semver('1.8.0')"}}}}",
    "$comment1": "The field below will be '1.9.0'",
    "test1": "{{"{{semver([1, 9, 0])"}}}}",
    "$comment2": "The field below will be '1.10.0'",
    "test2": "{{"{{semver(1, 10, 0)"}}}}"
  }
}
```
