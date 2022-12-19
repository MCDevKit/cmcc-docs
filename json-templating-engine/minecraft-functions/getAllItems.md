---
layout: page
grand_parent: JSON Templating Engine
parent: Minecraft functions
title: getAllItems
---

# getAllItems

Returns a list of vanilla item infos. Uses https://github.com/stirante/minecraft-item-db/blob/main/items.json

## Example

```json
{
  "$template": {
	// This will be a list of all vanilla item infos
    "test": "{{"{{getAllItems()"}}}}"
  }
}
```
