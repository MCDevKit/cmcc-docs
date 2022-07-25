---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: listLatestBPFiles
---

# listLatestBPFiles

Returns an array of paths to the latest vanilla behavior pack files in a given directory.

**This method is marked as unsafe. It can be disabled by certain environments.**

## Example

```json
{
  "$template": {
    "$comment": "The field below will be an array of absolute paths to latest spawn rules files across all vanilla packs",
    "test": "{{"{{listLatestBPFiles('spawn_rules')"}}}}"
  }
}
```
