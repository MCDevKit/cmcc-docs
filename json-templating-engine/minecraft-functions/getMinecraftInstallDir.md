---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: getMinecraftInstallDir
---

# getMinecraftInstallDir

Returns a path to the folder with Minecraft app. The value is cached after the first usage.

**This method is marked as unsafe. It can be disabled in certain environments.**

## Example

```json
{
  "$template": {
    "$comment": "The field below will most likely be 'C:\Program Files\WindowsApps\Microsoft.MinecraftUWP_<Minecraft version>__8wekyb3d8bbwe'",
    "test": "{{"{{getMinecraftInstallDir()"}}}}"
  }
}
```
