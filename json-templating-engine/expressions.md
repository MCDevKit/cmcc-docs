---
layout: page
parent: JSON Templating Engine
title: Expressions
nav_order: 2
---

# Expressions

## Object and Array Literals

JSON templates support object and array literals, enabling you to create complex structures:

### Array literals:

```json
{
  "$template": {
    "key": "{{"{{[1, 2, 3]"}}}}"
  }
}
```

### Object literals:

```json
{
  "$template": {
    "key": "{{"{{{'key1': 'value1', 'key2': 'value2'"}}}}}"
  }
}
```

## Backtick Template Strings

Backtick strings (`` ` `` ... `` ` ``) are multi-part strings with embedded expressions using `${...}` interpolation. Unlike the `{{...}}` notation used in JSON template keys and values, backtick strings let you embed multiple expressions inline within a single string expression:

```json
{
  "$template": {
    "greeting": "{{"{{=`Hello, ${name}! You have ${count} messages.`"}}}}"
  }
}
```

The `${...}` blocks support any expression. Escape sequences (`\n`, `\t`, `\\`, etc.) work the same as in regular strings.

## Lambda Expressions

Lambda expressions define inline functions, primarily used as arguments to higher-order functions like `map`, `filter`, `reduce`, and `sort`.

### Single-parameter lambda:

```json
{
  "$template": {
    "doubled": "{{"{{=[1, 2, 3].map(x => x * 2)"}}}}"
  }
}
```

### Multi-parameter lambda:

```json
{
  "$template": {
    "sum": "{{"{{=[1, 2, 3].reduce((acc, x) => acc + x, 0)"}}}}"
  }
}
```

### Block-body lambda:

Lambdas can have a block body with multiple statements using `return` to produce a value:

```json
{
  "$template": {
    "result": "{{"{{=[1, 2, 3, 4].filter(x => { return x % 2 == 0; })"}}}}"
  }
}
```

## Comments

Expressions support both line and block comments:

```json
{
  "$template": {
    "key": "{{"{{value + 1 // add one"}}}}"
  }
}
```

```json
{
  "$template": {
    "key": "{{"{{/* ignored */ value + 1"}}}}"
  }
}
```

## `this` Keyword

The `this` keyword represents the current scope, providing access to all properties within it. When not explicitly using the `.` or index operator, the keyword is implied. You can dynamically access fields with the `this` keyword:

```json
{
  "$template": {
    "$comment": "The value below evaluates to true",
    "key": "{{"{{this['key'] == this.key && this.key == key"}}}}"
  }
}
```
