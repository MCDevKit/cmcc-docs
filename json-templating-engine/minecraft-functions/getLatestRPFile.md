---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: getLatestRPFile
---

# getLatestRPFile

Returns a path to the latest resource pack file.

**This method is marked as unsafe. It can be disabled in certain environments.**
## Arguments

- `path` - The path to the file inside resource pack.

## Example

```json
{
  "$template": {
    "$comment": "The field below will most likely be 'C:\Program Files\WindowsApps\Microsoft.MinecraftUWP_<Minecraft version>__8wekyb3d8bbwe\data\resource_packs\vanilla_1.18.10\textures\entity\axolotl\axolotl_wild.png'",
    "test": "{{"{{getLatestRPFile('textures/entity/axolotl/axolotl_wild.png')"}}}}"
  }
}
```
