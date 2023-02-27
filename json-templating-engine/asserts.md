---
layout: page
parent: JSON Templating Engine
title: Assertions
nav_order: 3
---

# Assertions

Assertions are a compile-time actions, that can verify conditions, that can potentially result in an error or unusable template result.

The `$assert` key can be defined anywhere inside the `$template` object. It can be defined as a:
1. A string, that will be evaluated as a boolean expression
2. An object, that will evaluate `condition` as a boolean expression, and if it fails, the `message` property will be used as an error message
3. An array of strings, that will be evaluated in the order they are defined
4. An array of objects, that will be evaluated in the order they are defined

The `message` property is also a templated string. It can use any of the variables defined in the scope.

A simple assertion looks like this:

```jsonc
{
  "$scope": {
    "arr": []
  },
  "$template": {
    "$assert": "arr.count() > 0",
    "{{#arr}}": {
      "value{{index}}": "{{index}}"
    }
  }
}
```

This will result in compilation failure, because we require array `arr` to have at least one element.

# Providing human-readable error messages

Just failing can be enough, but it's always good to let the user know what went wrong. To do that, we can provide a human-readable error message:

```jsonc
{
  "$scope": {
    "arr": []
  },
  "$template": {
    "$assert": {
      "condition": "arr.count() > 0",
      "message": "Array arr must have at least one element"
    },
    "{{#arr}}": {
      "value{{index}}": "{{index}}"
    }
  }
}
```

# Using multiple assertions

Assertions can be used multiple times in a template. They are executed in the order they are defined.

```jsonc
{
  "$scope": {
    "arr": []
  },
  "$template": {
    "$assert": [
      {
        "condition": "arr.count() > 0",
        "message": "Array arr must have at least one element"
      },
      {
        "condition": "arr.count() < 10",
        "message": "Array arr must have less than 10 elements, but has {{arr.count()}}"
      }
    ],
    "{{#arr}}": {
      "value{{index}}": "{{index}}"
    }
  }
}
```