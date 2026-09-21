---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: listLatestRPFiles
---

# listLatestRPFiles

Returns an array of paths to the latest files in resource pack within given path.

Files stored inside a `.brarchive` (newer Minecraft versions) are returned as `<archive>.brarchive#/<file name>` paths.
## Arguments

- `path` - The path to the directory inside resource pack.

## Example

```json
{
  "$template": {
    "test": "{{"{{listLatestRPFiles('entity')"}}}}"
  }
}
```
