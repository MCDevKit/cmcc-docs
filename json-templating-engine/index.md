---
layout: page
title: JSON Templating Engine
has_children: true
---

# JSON Templating Engine

JSON Templating Engine is a simple templating engine, that speeds up generating large amounts of JSON files.
It follows usual JSON syntax and name should have an extension `.templ`.

Simple real life example:
```json
{
  "$template": {
    "pools": [
      {
        "rolls": 1,
        "entries": [
          {
            "$comment": "Iterate over range of 5 to 42 (inclusive)",
            "{{"{{#5..42"}}}}": {
              "type": "item",
              "name": "minecraft:potion",
              "weight": 1,
              "functions": [
                {
                  "function": "minecraft:set_data",
                  "$comment": "Set data field to the index value. '=' sign will force conversion to a number",
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

In JSON above, we want to create a loot table, that will include all possible potions. 
To do that, we repeat the block from field `{{"{{#5..42"}}}}` each time replacing `value` variable with number between 5 and 42.

To preview the result, you can try it [online](https://mcdevkit.com/#showcase) in box titled 'JSON Templating Engine'.