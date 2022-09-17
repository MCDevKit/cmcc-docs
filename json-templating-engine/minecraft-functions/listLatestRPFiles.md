---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: listLatestRPFiles
---

# listLatestRPFiles

Returns an array of paths to the latest files in resource pack within given path.
## Arguments

- `path` - The path to the directory inside resource pack.

## Example

{
  "$template": {
    "test": "{{"{{listLatestRPFiles('entity')"}}}}"
  }
}
