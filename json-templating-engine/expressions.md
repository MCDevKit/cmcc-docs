---
layout: page
parent: JSON Templating Engine
title: Expressions
nav_order: 6
---

# Expressions

This documentation page describes the various expressions and operators that you can use in JSON templates. These expressions allow you to generate dynamic content, evaluate conditions, and create complex structures.

## Range Operator

The range operator in JSON templates generates a sequence of numbers within a specified range. Here's the syntax:

```json
{
  "$template": {
    "key": "{{"{{start..end"}}}}"
  }
}
```

Both `start` and `end` values are inclusive, and they must be integers. The `start` value should be less than the `end` value. If you use floating-point numbers, the range operator will cast them to integers.

## Ternary Operator

The ternary operator in JSON templates evaluates a condition and returns one of two values based on the outcome. Here's the syntax:

```json
{
  "$template": {
    "key": "{{"{{condition ? valueIfTrue : valueIfFalse"}}}}"
  }
}
```

## Null Coalescing Operator

The null coalescing operator in JSON templates provides an alternative value if the initial expression evaluates to `null`. Here's the syntax:

```json
{
  "$template": {
    "key": "{{"{{expression ?? valueIfNull"}}}}"
  }
}
```

## Object and Array Literals

JSON templates support object and array literals, enabling you to create complex structures. Here's the syntax for both:

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

By incorporating these expressions and operators, you can create dynamic and versatile JSON templates to suit various use cases.

## `this` Keyword

The `this` keyword in JSON templates represents the current scope, providing access to all properties within it. When not explicitly using the `.` or index operator, the keyword is implied. You can dynamically access fields with the `this` keyword, as demonstrated in the example below:

```json
{
  "$template": {
    "$comment": "The value below evaluates to true"
    "key": "{{"{{this['key'] == this.key && this.key == key"}}}}"
  }
}
```

In this example, the `this` keyword is used to compare different ways of accessing the `key` property within the scope, ultimately resulting in a true evaluation.