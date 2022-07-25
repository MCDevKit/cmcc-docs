---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: getLatestRPFile
---

# getLatestRPFile

Returns a path to the latest vanilla resource pack file.

**This method is marked as unsafe. It can be disabled by certain environments.**

## Example

```json
{
  "$template": {
    "$comment": "The field below will most likely be 'C:\Program Files\WindowsApps\Microsoft.MinecraftUWP_<Minecraft version>__8wekyb3d8bbwe\data\resource_packs\vanilla_1.17.0\entity\axolotl.entity.json'",
    "test": "{{"{{getLatestRPFile('entity/axolotl.entity.json')"}}}}"
  }
}
```
