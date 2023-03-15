---
layout: page
parent: JSON Templating Engine
title: Template options
nav_order: 1
---

# Template Options

Template options provide flexibility in customizing the behavior of templates. Below are the key template options and their usage.

## Scope

The scope is the most crucial template option, allowing you to predefine variables before templating. Additionally, all variables within the local scope (defined inside the template) will also be templated.

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

You can define the scope globally in the data directory. All JSON files within that directory will be merged into a single object and used as the scope for all templates.

To add files and directories to the scope, use the `--scope <path>` CLI option.

## Files

The files option allows for generating multiple files from a single template. The following example creates five files:

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

## Copy

The copy option enables you to duplicate the contents of another file into the current file. The copied contents will be merged with modules and templates.

```json
{
  "$copy": "path/to/another/file.json"
}
```

Paths are templated strings, so you can use variables from the scope.

## Extend

The extend option allows merging one or more modules into the current template.

```json
{
  "$extend": ["module_name"]
}
```

Each element is a templated string, so you can conditionally add modules like this:

```json
{
  "$extend": ["{{"{{=someCondition ? ['module_name'] : []"}}}}"]
}
```

For more information on modules, refer to the [Modules](modules.md) section.