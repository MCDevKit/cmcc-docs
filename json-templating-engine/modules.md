---
layout: page
parent: JSON Templating Engine
title: Modules in JSON Templates
nav_order: 2
---

# Modules in JSON Templates

Modules are pre-defined templates that are not directly generated into the output. Instead, they are merged with other templates to simplify and streamline the creation of complex JSON structures. Modules are particularly useful for defining recurring parts of JSON across multiple templates.

## Sample Module Structure

Here is a basic example of a module:

```jsonc
{
  "$module": "module_name",
  "$template": {
    "test": "value"
  }
}
```

## Example Usage: Despawn Mechanic

A practical use case for a module is adding a despawn mechanic to an entity. The following example demonstrates how to create a module for this purpose:

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

To apply the despawn mechanic to a specific entity, such as a zombie, you can extend the zombie entity with the despawn module as shown below:

```jsonc
{
  "$extend": ["despawn"],
  "$copy": "{{"{{getLatestBPFile('entities/zombie.json')"}}}}"
}
```

This example defines a despawn module and extends a zombie entity with it, effectively adding the despawn mechanic to the entity.