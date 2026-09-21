---
layout: page
grand_parent: JSON Templating Engine
parent: File functions
title: loadMolang
---

# loadMolang

Loads a Molang file, evaluates its `#{...}` expressions and returns the minified Molang. The file is processed when the function is first called, so it can be used in `.jsonte` scripts. Results are cached for each path and parameters.

**This method is marked as unsafe. It can be disabled in certain environments.**
## Arguments

- `path` - The path to the Molang file to load.
- `params` - (optional) An object whose fields are available as variables in the file's expressions, in addition to the scope.

## Example

```json
{
  "$template": {
    "$comment": "rect.molang contains 'v.i = #{index};'. The field below will be 'v.i=3;'",
    "test": "{{"{{loadMolang('rect.molang', {'index': 3})"}}}}"
  }
}
```
