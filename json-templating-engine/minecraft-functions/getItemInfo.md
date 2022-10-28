---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: getItemInfo
---

# getItemInfo

Returns info in an object based on item ID. Uses https://github.com/stirante/minecraft-item-db/blob/main/items.json
## Arguments

- `id` - The item ID.
- `metadata` - (optional) The item data value.

## Example

```json
{
  "$template": {
    "test": "{{"{{getItemInfo('stone', 0)"}}}}"
  }
}
```
