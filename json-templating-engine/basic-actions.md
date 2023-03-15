---
layout: page
parent: JSON Templating Engine
title: Basic Actions
nav_order: 0
---

# Basic Actions Documentation

This documentation page provides an overview of basic actions available in the template language. The actions described here include: Value, Casting Value, Iteration, and Predicate.

## Value

To replace a template string with a value, simply use the double curly braces notation: `{{"{{variable"}}}}`. This action can be embedded within other text as follows: `key_{{"{{variable"}}}}`.

## Casting Value

Casting Value is an extension of the Value action that ensures the template string is of the same type as the underlying variable. To use this action, prepend the template string with an equal sign: `{{"{{=variable"}}}}`.

## Iteration

Iteration is an action that repeats a JSON element over an array or range. To initiate iteration, start the template string with a hashtag: `{{"{{#array"}}}}`.

During iteration, the following variables are exposed:

- `index`: The current index of iteration. To change it, use the format `{{"{{#array as value, i"}}}}`.
- `value`: The current element of iteration. To change it, use the format `{{"{{#array as element"}}}}`.

If the current iteration element is an object, its properties will be directly available without specifying the element name. For example, if you are iterating over an array of objects with the property `id`, instead of using `{{"{{value.id"}}}}`, you can simply use `{{"{{id"}}}}`.

## Predicate

A Predicate action includes its value only if the condition within it evaluates to true. To use this action, begin the template string with a question mark: `{{"{{?condition"}}}}`.

## Example Using All Actions

The example below iterates over a range of 0 to 5, creating a field named `key_<value>` for each number. The value of each field will be multiplied by 10 for numbers between 3 and 5, and remain the same for the rest of the numbers.

```json
{
  "$template": {
    "{{"{{#0..5"}}}}": {
      "{{"{{?value > 2 && value < 5"}}}}": {
        "key_{{"{{value"}}}}": "{{"{{=value * 10"}}}}"
      },
      "{{"{{?value <= 2 || value == 5"}}}}": {
        "key_{{"{{value"}}}}": "{{"{{=value"}}}}"
      }
    }
  }
}
```

The example above results in the following JSON:

```json
{
  "key_3": 30,
  "key_2": 2,
  "key_1": 1,
  "key_0": 0,
  "key_5": 5,
  "key_4": 40
}
```