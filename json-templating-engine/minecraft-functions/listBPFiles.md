---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: listBPFiles
---

# listBPFiles

Returns an array of paths to the latest files in behavior pack within given path.
## Arguments

- `path` - The path to the directory inside behavior pack.
- `version` - The version of Minecraft vanilla files to search for.

## Example

```json
{
  "$template": {
    "test": "{{"{{listBPFiles('entities', semver('1.17.30'))"}}}}"
  }
}
```
