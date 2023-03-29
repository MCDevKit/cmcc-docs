---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: getLatestBPFile
---

# getLatestBPFile

Returns a path to the latest behavior pack file.

**This method is marked as unsafe. It can be disabled in certain environments.**
## Arguments

- `path` - The path to the file inside behavior pack.
- `shouldFail` - (optional) Whether to throw an error and stop compilation or return null when the file is not found.

## Example

```json
{
  "$template": {
    "$comment": "The field below will most likely be 'C:\Program Files\WindowsApps\Microsoft.MinecraftUWP_<Minecraft version>__8wekyb3d8bbwe\data\behavior_packs\vanilla_1.18.10\entities\axolotl.json'",
    "test": "{{"{{getLatestBPFile('entities/axolotl.json')"}}}}"
  }
}
```
