---
layout: page
parent: JSON Templating Engine
title: Modules
nav_order: 2
---

# Modules

Modules are templates, that are not directly generated into the output, but rather are merged with other templates.
Modules are mainly used to define often repeating parts of json across many templates.

A sample module looks like this:

```jsonc
{
  "$module": "module_name",
  "$template": {
    "test": "value"
  }
}
```

# Example usage

A good example of a module is a module, that adds a despawn mechanic to an entity.

```jsonc
{
  "$module": "despawn",
  "$template": {
    "minecraft:entity": {
      "component_groups": {
        "despawn": {
          "minecraft:instant_despawn": {}
        }
      },
      "events": {
        "despawn": {
          "add": {
            "component_groups": ["despawn"]
          }
        }
      }
    }
  }
}
```

```jsonc
{
  "$extend": ["despawn"],
  "$copy": "C:\\Program Files\\WindowsApps\\Microsoft.MinecraftUWP_1.16.21060.0_x64__8wekyb3d8bbwe\\data\\behavior_packs\\vanilla\\entities\\zombie.json"
}
```

Above example will define a despawn module and copy a zombie entity extended with that despawn module.