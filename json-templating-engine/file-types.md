---
layout: page
parent: JSON Templating Engine
title: Other File Types
nav_order: 10
---

# Other File Types

Besides `.templ` templates and [`.jsonte` scripts](scripting.md), the engine can process three Minecraft-specific text formats: `.mcfunction`, `.molang`, and `.lang`. These are plain text files (not JSON), so instead of the `{{...}}` template syntax they use a `#`-based expression marker that is replaced inline with the evaluated result.

In all three formats the expression inside the marker uses the same syntax and [functions](index.md) as templates, runs against the current scope, and may span multiple lines. The expression must evaluate to a value (not `null` and not an [action](basic-actions.md)); the result is converted to a string and inserted in place.

| Extension     | Marker     | Extra processing                          |
| ------------- | ---------- | ----------------------------------------- |
| `.mcfunction` | `#{...}`   | None                                      |
| `.molang`     | `#{...}`   | `# ` comments stripped, output minified   |
| `.lang`       | `##{...}`  | Processed line by line                    |

## `.mcfunction`

Minecraft function files use the `#{...}` marker. The whole file is processed at once and each marker is replaced with its evaluated value. Everything outside a marker - including `#` comment lines - is left untouched.

```mcfunction
# Place a block that can sit on dirt or stone
/give @s diamond_block 1 0 {"minecraft:can_place_on":{"blocks":#{["dirt", "stone"]}}}
say "#{'Hello World'}"
```

Result:

```mcfunction
# Place a block that can sit on dirt or stone
/give @s diamond_block 1 0 {"minecraft:can_place_on":{"blocks":["dirt","stone"]}}
say "Hello World"
```

Because expressions may span multiple lines, you can build commands programmatically:

```mcfunction
#{
  (1..10)
    .map(x => x * 2)
    .filter(x => mod(x, 3) == 0)
    .join(", ")
}
```

Result:

```mcfunction
6, 12, 18
```

## `.molang`

Molang files also use the `#{...}` marker, but the engine performs two extra steps:

1. **Comment stripping** - `# ` line comments (a `#` followed by a space) are removed. A `#{` expression marker is never treated as a comment, and `#` characters inside string literals are left alone.
2. **Minification** - the output has insignificant whitespace removed and the long accessor names are shortened: `variable` → `v`, `query` → `q`, `context` → `c`, `temp` → `t`.

```molang
# initial speed
variable.speed = #{1 + 1};
return variable.speed;
```

Result:

```molang
v.speed=2;return v.speed;
```

Files with no expressions are still comment-stripped and minified.

## `.lang`

Minecraft lang files use the `##{...}` marker and are processed **line by line**. Each line is handled independently, so an unterminated marker is reported with its line number. Lines without a marker - including `## comment` lines, since `##` must be immediately followed by `{` to start an expression - pass through unchanged.

```lang
## Greeting strings
item.example.name=##{'Hello ' + 'World'}
```

Result:

```lang
## Greeting strings
item.example.name=Hello World
```
