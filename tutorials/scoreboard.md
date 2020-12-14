---
layout: page
parent: Tutorials
title: Physical Scoreboard
---

# Physical Scoreboard

This tutorial walks you through how you could create a physical scoreboard in your map.

![](https://s3.eu-central-1.amazonaws.com/files.stirante.com/2020-12-14_12-25-21.png)

This scoreboard is done using particles with single characters. 
Those particles are positioned using a marker entity, which is moved relatively.

## Project setup

```
cmcc init "Scores example" "Example demonstrating how to create simple score board"
```

## Marker entity

```json
{
  "format_version": "1.12.0",
  "minecraft:entity": {
    "description": {
      "identifier": "example:marker",
      "is_spawnable": false,
      "is_summonable": true
    },
    "component_groups": {
      "despawn": {
        "minecraft:instant_despawn": {}
      }
    },
    "events": {
      "despawn": {
        "add": {
          "component_groups": [
            "despawn"
          ]
        }
      }
    },
    "components": {
      "minecraft:type_family": {
        "family": [
          "marker"
        ]
      },
      "minecraft:health": {
        "value": 100,
        "max": 100
      },
      "minecraft:fire_immune": true,
      "minecraft:knockback_resistance": {
        "value": 100,
        "max": 100
      },
      "minecraft:damage_sensor": {
        "triggers": {
          "on_damage": {
            "filters": {
              "none_of": [
                {"test": "has_damage", "value": "none"},
                {"test": "has_damage", "value": "override"}
              ]
            }
          },
          "deals_damage": false
        }
      },
      "minecraft:physics": {
        "has_gravity": false
      },
      "minecraft:collision_box": {
        "width": 0,
        "height": 0
      },
      "minecraft:pushable": {
        "is_pushable": false,
        "is_pushable_by_piston": false
      },
      "minecraft:push_through": {
        "value": 1
      }
    }
  }
}
```

The marker entity is immortal (except void and /kill command) and immovable. In addition, it will quietly despawn, when `despawn` event has been triggered.

## Character particles

All character particles will be almost the same. To avoid copy-pasting them 10 times, we will make use of JSON templating engine.

First we need to define data for the engine. To do this, we edit `project.json` file and add this field:

```json
  "scope": {
    "particles": [
      {
        "name": "counter_0",
        "texture": "counter/0"
      },
      {
        "name": "counter_1",
        "texture": "counter/1"
      },
      {
        "name": "counter_2",
        "texture": "counter/2"
      },
      {
        "name": "counter_3",
        "texture": "counter/3"
      },
      {
        "name": "counter_4",
        "texture": "counter/4"
      },
      {
        "name": "counter_5",
        "texture": "counter/5"
      },
      {
        "name": "counter_6",
        "texture": "counter/6"
      },
      {
        "name": "counter_7",
        "texture": "counter/7"
      },
      {
        "name": "counter_8",
        "texture": "counter/8"
      },
      {
        "name": "counter_9",
        "texture": "counter/9"
      },
      {
        "name": "counter_dot",
        "texture": "counter/dot"
      },
      {
        "name": "leaderboard",
        "texture": "counter/leaderboard",
        "size": [1.54, 0.16],
        "uv": {
          "texture_width": 77,
          "texture_height": 8,
          "uv": [0, 0],
          "uv_size": [77, 8]
        }
      }
    ]
  }
```

Next we need to actually create a template particle. All json template names must end with `.templ`. 
We create a `counter.particle.templ` file:

```jsonc
{
  "$files": {
    "array": "particles",
    "fileName": "{{name}}.particle"
  },
  "$template": {
    "format_version": "1.10.0",
    "particle_effect": {
      "description": {
        "identifier": "example:{{name}}",
        "basic_render_parameters": {
          "material": "particles_alpha",
          "texture": "textures/particles/{{texture}}"
        }
      },
      "components": {
        "minecraft:emitter_rate_instant": {
          "num_particles": 1
        },
        "minecraft:emitter_lifetime_looping": {
          "active_time": 1
        },
        "minecraft:emitter_shape_point": {
          "direction": [-0.5, 0, 0]
        },
        "minecraft:particle_lifetime_expression": {
          "max_lifetime": 1.1
        },
        "minecraft:particle_initial_speed": 1,
        "minecraft:particle_motion_parametric": {
          "relative_position": [0, 0, 0]
        },
        "minecraft:particle_appearance_billboard": {
          "{{?size}}": {
            "size": "{{size}}"
          },
          "{{?!size}}": {
            "size": [0.15, 0.15]
          },
          "facing_camera_mode": "direction_z",
          "{{?uv}}": {
            "uv": "{{uv}}"
          },
          "{{?!uv}}": {
            "uv": {
              "texture_width": 8,
              "texture_height": 8,
              "uv": [0, 0],
              "uv_size": [8, 8]
            }
          }
        },
        "minecraft:particle_appearance_lighting": {}
      }
    }
  }
}
```

`$files` object specifies how files will be generated. Our current configuration will generate a separate json file for every element in `particles` array, and the name of the file will begin with `name` field of the element. Particle identifiers will also include `name` field.

In `minecraft:particle_appearance_billboard` component, `{{?size}}` means, that if the `size` field in data is not null, it will add the content to the current object. `{{?!size}}` is the same predicate, but negated, so content will be added if `size` field is null.

## Code

Now it's time to get to the code. First we create a file named `board.mcc`
```
func displayScore(marker:context , n:int , score:int , denominator:int) {
    // Show place number
    showChar(marker, n);
    for (marker) {
        >>tp @s ~~~0.25
    }
    // Show place dot
    showChar(marker, 10);
    for (marker) {
        >>tp @s ~~~0.3
    }
    // Show score
    do {
        let digit = score / denominator;
        score = score % denominator;
        denominator = denominator / 10;
        for (marker) {
            >>tp @s ~~~0.25
        }
        showChar(marker, digit);
    } while (denominator > 0);
}

// Simple function, that shows character particle at marker location
func showChar(marker:context , digit:int) {
    switch (digit) {
        case 0 {
            for (marker) {
                >>particle example:counter_0 ~~~
            }
        }
        case 1 {
            for (marker) {
                >>particle example:counter_1 ~~~
            }
        }
        case 2 {
            for (marker) {
                >>particle example:counter_2 ~~~
            }
        }
        case 3 {
            for (marker) {
                >>particle example:counter_3 ~~~
            }
        }
        case 4 {
            for (marker) {
                >>particle example:counter_4 ~~~
            }
        }
        case 5 {
            for (marker) {
                >>particle example:counter_5 ~~~
            }
        }
        case 6 {
            for (marker) {
                >>particle example:counter_6 ~~~
            }
        }
        case 7 {
            for (marker) {
                >>particle example:counter_7 ~~~
            }
        }
        case 8 {
            for (marker) {
                >>particle example:counter_8 ~~~
            }
        }
        case 9 {
            for (marker) {
                >>particle example:counter_9 ~~~
            }
        }
        case 10 {
            for (marker) {
                >>particle example:counter_dot ~~~
            }
        }
    }
}
```

After that we edit the `main.mcc` file
```
import "board.mcc"

define timer;
define s1;
define s2;
define s3;
define s4;
define s5;

func start() {
    debug("RAM reset");
    // init scores
    s1 = 19876;
    s2 = 777;
    s3 = 20;
    s4 = 1;
    s5 = 0;
}

func update() {
    // Increment timer every tick and if 20 ticks has passed, we display score and reset the timer
    timer++;
    if (timer >= 20) {
        // Coordinates were adjusted so it looks like the particles are attached to the wall
        >>particle example:leaderboard 180.90 72.5 141.5
        >>event entity @e[type=example:marker] despawn
        >>summon example:marker 180.95 72.0 139.0
        context marker = @e[type=example:marker];
        displayScore(marker, 1, s1, 10000);
        // Every time we draw another score, we reset x and z marker position and move relatively in y axis
        for (marker) {
            >>tp @s 180.95 ~-0.4 139.0
        }
        displayScore(marker, 2, s2, 10000);
        for (marker) {
            >>tp @s 180.95 ~-0.4 139.0
        }
        displayScore(marker, 3, s3, 10000);
        for (marker) {
            >>tp @s 180.95 ~-0.4 139.0
        }
        displayScore(marker, 4, s4, 10000);
        for (marker) {
            >>tp @s 180.95 ~-0.4 139.0
        }
        displayScore(marker, 5, s5, 10000);
        // Clean up marker after drawing score
        >>event entity @e[type=example:marker] despawn
        timer = 0;
    }
}
```

## World setup

Execute the `cmcc install` command.

Add both behavior and resource pack to the world. Place a repeating command block and set its command to `function main` and `Redstone` to `Always active`.

For aesthetics, add a wall of black wool behind the scores.

Finished example: [Download](https://s3.eu-central-1.amazonaws.com/files.stirante.com/scores-example.zip)