---
layout: page
title: JSON Templating Engine
has_children: true
---

# JSON Templating Engine

The JSON Templating Engine is a user-friendly templating engine designed to streamline the process of generating large numbers of JSON files. It adheres to standard JSON syntax, and template files should have the `.templ` extension.

Several other file types are also supported:

| Extension     | Expression syntax | Notes                                                                                           |
| ------------- | ----------------- | ----------------------------------------------------------------------------------------------- |
| `.templ`      | `{{...}}`         | Primary format - full JSON template support.                                                    |
| `.modl`       | `{{...}}`         | Module file - merged into other templates instead of being generated. See [Modules](modules.md). |
| `.jsonte`     | (script)          | Script file executed against the scope before templates run. See [Scripting](scripting.md).     |
| `.mcfunction` | `#{...}`          | Minecraft function file - see [Other File Types](file-types.md).                                   |
| `.molang`     | `#{...}`          | Molang file - comments stripped, output minified. See [Other File Types](file-types.md).                  |
| `.lang`       | `##{...}`         | Minecraft lang file - see [Other File Types](file-types.md).                                 |

To access an interactive tutorial, [click here](https://mcdevkit.com/tutorial).

## Example: Creating a Loot Table with All Possible Potions

Below is a real-life example demonstrating how to create a loot table that includes all possible potions using the JSON Templating Engine:

```json
{
  "$template": {
    "pools": [
      {
        "rolls": 1,
        "entries": [
          {
            "$comment": "Iterate over the range of 5 to 42 (inclusive)",
            "{{"{{#5..42"}}}}": {
              "type": "item",
              "name": "minecraft:potion",
              "weight": 1,
              "functions": [
                {
                  "function": "minecraft:set_data",
                  "$comment": "Set the data field to the index value. The '=' sign forces conversion to a number",
                  "data": "{{"{{=value"}}}}"
                }
              ]
            }
          }
        ]
      }
    ]
  }
}
```

In the JSON example above, we want to create a loot table that includes all possible potions. To achieve this, we repeat the block from the field `{{"{{#5..42"}}}}` and replace the `value` variable with a number between 5 and 42 for each iteration.

You can preview the result [online](https://mcdevkit.com/#showcase) in the 'JSON Templating Engine' section.