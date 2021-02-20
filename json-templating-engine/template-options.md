---
layout: page
parent: JSON Templating Engine
title: Template options
---

# Template options

There are a number of options, you can define in a template. 

## Scope

This is the most important template options. It allows you to set some variables before templating. 

```json
{
  "$scope": {
    "settings": {
      "setting1": "value"
    }
  },
  "$template": {
    "$comment": "The field below will be 'value'",
    "test": "{{"{{settings.setting1"}}}}"
  }
}
```

The scope can also be defined globally in `project.json` file like this:

```json
{
  "build": {
    "file_name": "one-pack.mcaddon"
  },
  "install": {
    "save_folder": "",
    "install_in_dev": true
  },
  "name": "Pack name",
  "description": "Pack description",
  "ram_entity_identifier": "cl:ram",
  "scope": {
    "settings": {
      "setting1": "value"
    }
  }
}
```

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

A minor option, that allows for completely copying contents of another file into current file.

```json
{
  "$copy": "path/to/another/file.json"
}
```