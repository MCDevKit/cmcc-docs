---
layout: page
parent: JSON Templating Engine
title: Order of operations
nav_order: 8
---

# Order of Operations in JSON Templates

This page provides a comprehensive understanding of the order of operations in JSON templates. Grasping the order of operations is crucial as it dictates the sequence in which templates, modules, and copy expressions are evaluated, which, in turn, affects the final output of your template.

Bear in mind that each merge operation can overwrite the contents of the previous merge operation, making the order of operations vital.

## 1. Copy Expressions

Copy expressions are evaluated first, enabling you to duplicate the contents of another file into the current file.

```json
{
  "$copy": "path/to/another/file.json"
}
```

## 2. Modules

Modules are evaluated following copy expressions. They allow you to enhance the current file with the contents of a module.

```json
{
  "$extend": ["module_name"]
}
```

Modules are evaluated and merged sequentially, according to the order in which they are defined (from top to bottom).

## 3. Templates

Lastly, templates are evaluated, permitting you to establish the contents of the current file.

```json
{
  "$template": {
    "test": "value"
  }
}
```

By understanding and utilizing the proper order of operations in JSON templates, you can effectively manage the evaluation and merging of copy expressions, modules, and templates to generate the desired output.