---
layout: page
parent: JSON Templating Engine
title: Boolean Expressions
nav_order: 7
---

# Boolean Expressions

This page provides an overview of boolean expressions in JSON templates, including comparison operators, logical operators, truthy and falsy values. While JSON template expressions share similarities with JavaScript expressions, there are some key differences.

## Comparison Operators

JSON templates support the following comparison operators:

| Operator | Description              | Notes                                                 |
| -------- | ------------------------ | ----------------------------------------------------- |
| `==`     | Equal to                 | No type coercion is performed with this operator      |
| `!=`     | Not equal to             |                                                       |
| `>`      | Greater than             | Applies to numbers, booleans, and semantic versioning |
| `>=`     | Greater than or equal to | Applies to numbers, booleans, and semantic versioning |
| `<`      | Less than                | Applies to numbers, booleans, and semantic versioning |
| `<=`     | Less than or equal to    | Applies to numbers, booleans, and semantic versioning |

### Examples

In the following template, `key` evaluates to `false` because no type coercion is performed:

```json
{
  "$template": {
    "key": "{{"{{1 == '1'"}}}}"
  }
}
```

In this example, `key` evaluates to `true` because the `>` operator applies to semantic versioning:

```json
{
  "$template": {
    "key": "{{"{{semver('1.0.1') > semver('1.0.0')"}}}}"
  }
}
```

## Logical Operators

JSON templates support these logical operators:

| Operator | Description | Notes                                                                                     |
| -------- | ----------- | ----------------------------------------------------------------------------------------- |
| `&&`     | Logical AND | Short-circuiting operator; stops evaluating expressions after the first falsy expression  |
| `||`     | Logical OR  | Short-circuiting operator; stops evaluating expressions after the first truthy expression |
| `!`      | Logical NOT |                                                                                           |

### Examples

In this example, the `&&` operator stops evaluating expressions after the first falsy expression, so `key` evaluates to `false` and `expensiveFunction()` is not called:

```json
{
  "$template": {
    "key": "{{"{{false && expensiveFunction()"}}}}"
  }
}
```

In this example, the `||` operator stops evaluating expressions after the first truthy expression, so `key` evaluates to `true` and `expensiveFunction()` is not called:

```json
{
  "$template": {
    "key": "{{"{{true || expensiveFunction()"}}}}"
  }
}
```

## Truthy and Falsy Values

In JSON templates, the following values are considered falsy and evaluate to `false` when used in a boolean expression:

- `false`
- `0`
- `null`
- `[]` (empty array)
- `{}` (empty object)
- `''` (empty string or a string containing only newlines and carriage returns)

All other values are considered truthy.