---
layout: page
parent: JSON Templating Engine
title: Basic Actions
---

# Basic Actions

## Value

The most basic operation, you can do is replace a template string with a value e.g. `{{"{{variable"}}}}`.
This action can be added in the middle of other text like this `key_{{"{{variable"}}}}`.

## Casting Value

An extension of the value action is casting value, which will force the template string to be a number. 
It is used by adding `=` character at the beginning of a template string like so `{{"{{=variable"}}}}`.

## Iteration

Iteration is an action, that will repeat a JSON element over an array, or a range. 
It is triggered by beginning a template string with `#` e.g. `{{"{{#array"}}}}`.

Every iteration will also expose variables:
 - index: a current index of iteration
 - value: a current element of iteration (this can be changed like this `{{"{{#array as element"}}}}`)

Additionally, if the current iteration element is an object, all it's properties will be available without specifying the element name.
So for example if you are iteration over array of objects and all objects have properties `id`, instead of using `{{"{{value.id"}}}}` you can just use `{{id}}`.

## Predicate

Predicate will add its value only if the condition inside it is true.
It is used by adding `?` character at the beginning of a template string like so `{{"{{?condition"}}}}`.

## Example using all actions

Example below will iterate over range of 0 to 5 and for every number, it will create a field named `key_<value>`.
The value of each field will be multiplied by 10 for numbers between 3 and 5 and the same number for rest of the numbers.

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

Example above will result in this JSON:
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