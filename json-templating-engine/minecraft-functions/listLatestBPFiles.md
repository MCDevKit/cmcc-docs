---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: listLatestBPFiles
---

# listLatestBPFiles

Returns an array of paths to the latest files in behavior pack within given path.
## Arguments

- `path` - The path to the directory inside behavior pack.

## Example

{
  "$template": {
    "test": "{{"{{listLatestBPFiles('entities')"}}}}"
  }
}
