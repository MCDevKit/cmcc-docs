---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: listRPFiles
---

# listRPFiles

Returns an array of paths to the latest files in resource pack within given path.

Files stored inside a `.brarchive` (newer Minecraft versions) are returned as `<archive>.brarchive#/<file name>` paths.
## Arguments

- `path` - The path to the directory inside resource pack.
- `version` - The version of Minecraft vanilla files to search for.

## Example

```json
{
  "$template": {
    "test": "{{"{{listRPFiles('entity', semver('1.17.30'))"}}}}"
  }
}
```
