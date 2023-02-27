---
layout: page
parent: JSON Templating Engine
title: Template options
nav_order: 1
---

# Template options

There are a number of options, you can define in a template. 

## Scope

This is the most important template options. It allows you to set some variables before templating. Additionally all variables inside the local scope (the one defined inside tempalate) are templated as well.

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

The scope can also be defined globally in data directory. All json files inside that directory will be merged into one object, and that object will be used as a scope for all templates.

Files and directories can be added to the scope with `--scope <path>` CLI option.

## Files

A very important option, that allows for creating multiple files from one template. The example below will create 5 files.

```json
{
  "$files": {
    "array": "1..5",
    "fileName": "test_{{"{{value"}}}}"
  },
  "$template": {
    "test": "{{value}}"
  }
}
```

## Copy

An option, that allows for completely copying contents of another file into current file. Copied contents are merged with modules and template.

```json
{
  "$copy": "path/to/another/file.json"
}
```

The path is a templated string, so you can use variables from the scope.

## Extend

An option, that allows for merging one or more modules into the current template.

```json
{
  "$extend": ["module_name"]
}
```

Each element is a templated string, so you can add modules conditionally like this:

```json
{
  "$extend": ["{{"{{=someCondition ? ['module_name'] : []"}}}}"]
}
``` 

Further information on modules can be found in the [Modules](modules.md) section.