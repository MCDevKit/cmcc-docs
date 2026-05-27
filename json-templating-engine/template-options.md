---
layout: page
parent: JSON Templating Engine
title: Template Options
nav_order: 4
---

# Template Options

Template options control how a template is evaluated. They are top-level keys placed alongside `$template` in a `.templ` file.

For composing templates with other files and modules, see [Modules](modules.md).

## `$scope`

Predefines variables that are available during templating. Values inside `$scope` are themselves evaluated as template expressions.

```json
{
  "$scope": {
    "settings": {
      "setting1": "value",
      "setting2": "{{"{{pi()"}}}}"
    }
  },
  "$template": {
    "$comment": "The field below will be 'value'",
    "test": "{{"{{settings.setting1"}}}}"
  }
}
```

You can also define a global scope by pointing the `--scope` CLI option at a file or directory. All JSON files in that directory are merged into a single object and made available to every template.

## `$files`

Generates multiple output files from a single template. The `array` field is an **expression string** evaluated at runtime - it must produce an array. The `fileName` field is a templated string used as the output filename for each element.

The following example creates five files named `test_1.json` through `test_5.json`:

```json
{
  "$files": {
    "array": "1..5",
    "fileName": "test_{{"{{value"}}}}"
  },
  "$template": {
    "test": "{{"{{value"}}}}"
  }
}
```

During each iteration the following variables are available in scope:

- `value`: the current array element
- `index`: the zero-based position

If an element is an object, its properties are additionally pushed into scope directly (same behaviour as [Iteration](basic-actions.md#iteration)).

The `array` expression can reference any scope variable or expression that produces an array:

```json
{
  "$files": {
    "array": "items",
    "fileName": "{{"{{value.id"}}}}"
  },
  "$template": {
    "name": "{{"{{value.name"}}}}"
  }
}
```

## `$comment`

Adds a human-readable annotation anywhere inside a `$template` object. It is silently discarded and never appears in the output.

```json
{
  "$template": {
    "$comment": "This section sets up the entity components",
    "minecraft:entity": {}
  }
}
```
