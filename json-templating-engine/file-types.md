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
2. **Minification** - the output has insignificant whitespace removed and the long accessor names are shortened: `variable` → `v`, `query` → `q`, `context` → `c`, `temp` → `t`. Redundant parentheses are also removed and numbers are written in their shortest form, for example `1.0` becomes `1`.

```molang
# initial speed
variable.speed = #{1 + 1.0};
return (query.anim_time * variable.speed);
```

Result:

```molang
v.speed=2;return q.anim_time*v.speed;
```

Files with no expressions are still comment-stripped and minified.

### Loading Molang into templates and scripts

Use `loadMolang` with the path of a `.molang` file to insert the processed result into a template or a [script](scripting.md). The file is processed when it is first loaded, with the scope built so far, and the result is cached:

```json
{
  "$template": {
    "creation_expression": "{{"{{loadMolang('data/jsonte/molang/particle_creation.molang')"}}}}"
  }
}
```

The optional second argument is an object whose fields are available as variables in the file's expressions. Use it to generate several variants of one file. With this `rect.molang`:

```molang
v.i = #{index};
```

`loadMolang('data/jsonte/molang/rect.molang', {'index': 3})` returns `v.i=3;`. Expressions that do not use any of the parameters are evaluated only once, no matter how many variants are loaded.

For `.molang` files in a scope directory, [loadText](file-functions/loadText.md) also returns the processed result, like `loadMolang` without parameters. For other files, `loadText` returns the file unchanged.

### Validation

The engine checks that every processed `.molang` file is valid Molang, following the rules Minecraft Bedrock applies when it loads Molang. For example:

- Every statement inside `{ }` must end with `;`.
- An expression that contains `=` or `;` must end with `;`.
- The left-hand side of `??` must be a variable, such as `v.x ?? 0`. `q.x ?? 0` is not allowed.

A file that is not valid Molang stops the compilation with an error. The error shows the line and column in the processed file:

```
The molang file data\jsonte\molang\rect.molang is not valid Molang: unknown identifier '__RECT_INDEX__' — expected math./query./variable./temp./context. (line 3, column 7 of the processed file: v.i = __RECT_INDEX__;). Use --disable-molang-validation to output it anyway.
```

Some files are fragments that are completed later, for example a file with a placeholder that a function replaces before the Molang is used. To allow them, use the `--disable-molang-validation` [CLI option](cli.md). With this option, such files are output without an error, with only whitespace removed and the accessor names shortened. Valid files are still fully minified.

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
