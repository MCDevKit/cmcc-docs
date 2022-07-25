---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: listLatestRPFiles
---

# listLatestRPFiles

Returns an array of paths to the latest vanilla resource pack files in a given directory.

**This method is marked as unsafe. It can be disabled by certain environments.**

## Example

```json
{
  "$template": {
    "$comment": "The field below will be an array of absolute paths to latest camera files across all vanilla packs",
    "test": "{{"{{listLatestRPFiles('cameras')"}}}}"
  }
}
```
