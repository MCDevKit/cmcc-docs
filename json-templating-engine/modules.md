---
layout: page
parent: JSON Templating Engine
title: Modules
nav_order: 5
---

# Modules

Modules are pre-defined templates that are not directly generated into the output. Instead, they are merged with other templates to simplify and streamline the creation of complex JSON structures. Modules are particularly useful for defining recurring parts of JSON across multiple templates.

## Defining a Module

A module is a `.templ` file with a `$module` key that gives it a name:

```jsonc
{
  "$module": "module_name",
  "$template": {
    "test": "value"
  }
}
```

## Extending a Module

Use `$extend` to merge one or more modules into the current template. The current template's values take precedence over the module's values for any conflicting keys (see [Merge Operations](merge-operations.md)).

```json
{
  "$extend": ["module_name"],
  "$template": {
    "extra_key": "value"
  }
}
```

Each element is a templated string, so you can conditionally include modules:

```json
{
  "$extend": ["{{"{{=someCondition ? ['module_name'] : []"}}}}"]
}
```

## Copying a File

Use `$copy` to pull in the contents of another file and merge it as the base of the current template. The copied file's contents are treated as the starting point; modules and `$template` are then merged on top.

```json
{
  "$copy": "path/to/another/file.json"
}
```

Paths are templated strings, so you can use scope variables:

```json
{
  "$copy": "{{"{{getLatestBPFile('entities/zombie.json')"}}}}"
}
```

To copy multiple files, pass an array - they are merged in order:

```json
{
  "$copy": ["path/to/base.json", "path/to/override.json"]
}
```

## Example: Adding a Despawn Mechanic

Define the mechanic once as a module:

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

Then apply it to any entity by copying the entity file and extending with the module:

```jsonc
{
  "$extend": ["despawn"],
  "$copy": "{{"{{getLatestBPFile('entities/zombie.json')"}}}}"
}
```

This copies the zombie entity definition and merges the despawn mechanic on top.
