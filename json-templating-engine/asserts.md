---
layout: page
parent: JSON Templating Engine
title: Assertions
nav_order: 3
---

# Assertions

Assertions are compile-time actions used to verify conditions that could potentially result in an error or produce an unusable template output.

The `$assert` key can be placed anywhere within the `$template` object and can be defined as:

1. A string to be evaluated as a boolean expression
2. An object that evaluates the `condition` as a boolean expression; if the condition fails, the `message` property serves as an error message
3. An array of strings to be evaluated in the order they are defined
4. An array of objects to be evaluated in the order they are defined

The `message` property is also a templated string that can use any variables defined in the scope.

## Simple Assertion Example

```jsonc
{
  "$scope": {
    "arr": []
  },
  "$template": {
    "$assert": "arr.count() > 0",
    "{{"{{#arr"}}}}": {
      "value{{"{{index"}}}}": "{{"{{index"}}}}"
    }
  }
}
```

This example will result in a compilation failure because it requires the array `arr` to have at least one element.

## Providing Human-readable Error Messages

To provide a clear error message to the user, use the `message` property:

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
    "{{"{{#arr"}}}}": {
      "value{{"{{index"}}}}": "{{"{{index"}}}}"
    }
  }
}
```

## Using Multiple Assertions

You can use multiple assertions in a template, and they will be executed in the order they are defined:

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
        "message": "Array arr must have less than 10 elements, but has {{"{{arr.count()"}}}}"
      }
    ],
    "{{"{{#arr"}}}}": {
      "value{{"{{index"}}}}": "{{"{{index"}}}}"
    }
  }
}
```