---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: findItemInfoById
---

# findItemInfoById

Returns info in an object based on fuzzy matching item ID. Uses https://github.com/stirante/minecraft-item-db/blob/main/items.json
## Arguments

- `id` - The item ID.
- `metadata` - (optional) The item data value.

## Example

```json
{
  "$template": {
// {"id":"minecraft:blue_glazed_terracotta","legacyId":231,"metadata":0,"maxDurability":0,"damage":0,"armor":0,"maxStackSize":64,"tags":[],"category":"construction","nutrition":0,"fuelDuration":0,"aliases":["minecraft:glazedTerracotta.blue"],"nameKey":"tile.glazedTerracotta.blue.name","langName":"Blue Glazed Terracotta"}
    "test": "{{"{{findItemInfoById('blue_terracotta', 0)"}}}}"
  }
}
```
