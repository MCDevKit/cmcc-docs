---
layout: page
parent: JSON Templating Engine
title: Operators
nav_order: 1
---

# Operators

## Arithmetic Operators

JSON templates support the standard arithmetic operators:

| Operator | Description    | Notes                                                                     |
| -------- | -------------- | ------------------------------------------------------------------------- |
| `+`      | Addition       | Also concatenates strings and merges arrays/objects (see [Types](types.md)) |
| `-`      | Subtraction    |                                                                           |
| `*`      | Multiplication |                                                                           |
| `/`      | Division       | Integer division when both operands are integers                          |
| `-x`     | Unary negation |                                                                           |

## Range Operator

The range operator generates a sequence of numbers within a specified range:

```json
{
  "$template": {
    "key": "{{"{{start..end"}}}}"
  }
}
```

Both `start` and `end` values are inclusive, and they must be integers. The `start` value should be less than the `end` value. If you use floating-point numbers, the range operator will cast them to integers.

## Ternary Operator

The ternary operator evaluates a condition and returns one of two values based on the outcome:

```json
{
  "$template": {
    "key": "{{"{{condition ? valueIfTrue : valueIfFalse"}}}}"
  }
}
```

## Null Coalescing Operator

The null coalescing operator provides an alternative value if the initial expression evaluates to `null`:

```json
{
  "$template": {
    "key": "{{"{{expression ?? valueIfNull"}}}}"
  }
}
```

## Optional Chaining

The optional chaining operator (`?.`) safely accesses a property or index, returning `null` instead of throwing an error when the field or index does not exist. This includes the case where the target itself is `null`.

### Optional property access:

```json
{
  "$template": {
    "key": "{{"{{obj?.field"}}}}"
  }
}
```

### Optional index access:

```json
{
  "$template": {
    "key": "{{"{{arr?[0]"}}}}"
  }
}
```

Without `?`, accessing a missing field or a field on `null` throws an error. With `?`, the result is `null`. For example, `{}.missing` is an error, while `{}?.missing` returns `null`.

## Spread Operator

The spread operator (`...`) expands an array into individual elements. It can be used in array literals and in function calls.

### Spread in array literals:

```json
{
  "$template": {
    "combined": "{{"{{=[...arr1, 4, 5, ...arr2"]}}}}"}
  }
}
```

### Spread in function calls:

```json
{
  "$template": {
    "result": "{{"{{someFunction(...args)"}}}}"
  }
}
```

## Assignment Operators

Assignment operators are used in [scripting contexts](scripting.md) and in the `$scope` initializer to mutate variables.

| Operator | Description                     |
| -------- | ------------------------------- |
| `=`      | Assign a value                  |
| `+=`     | Add and assign (or concatenate) |

```json
{
  "$template": {
    "key": "{{"{{obj.count = obj.count + 1"}}}}"
  }
}
```

Assignment returns the assigned value, so it can be used inside larger expressions.

## Comparison Operators

JSON templates support the following comparison operators. Note that `==` performs no type coercion.

| Operator | Description              | Notes                                                 |
| -------- | ------------------------ | ----------------------------------------------------- |
| `==`     | Equal to                 | No type coercion                                      |
| `!=`     | Not equal to             |                                                       |
| `>`      | Greater than             | Applies to numbers, booleans, and semver              |
| `>=`     | Greater than or equal to | Applies to numbers, booleans, and semver              |
| `<`      | Less than                | Applies to numbers, booleans, and semver              |
| `<=`     | Less than or equal to    | Applies to numbers, booleans, and semver              |

```json
{
  "$template": {
    "$comment": "false - no type coercion",
    "strict": "{{"{{1 == '1'"}}}}",
    "$comment2": "true - semver comparison",
    "newer": "{{"{{semver('1.0.1') > semver('1.0.0')"}}}}"
  }
}
```

## Logical Operators

| Operator | Description  | Notes                                                                                     |
| -------- | ------------ | ----------------------------------------------------------------------------------------- |
| `&&`     | Logical AND  | Short-circuiting: stops after the first falsy expression                                  |
| `\|\|`   | Logical OR   | Short-circuiting: stops after the first truthy expression                                 |
| `!`      | Logical NOT  |                                                                                           |

Short-circuiting means the right side is not evaluated if the result is already determined:

```json
{
  "$template": {
    "$comment": "expensiveFunction() is never called",
    "key": "{{"{{false && expensiveFunction()"}}}}"
  }
}
```

## Truthy and Falsy Values

The following values are considered falsy:

- `false`
- `0`
- `null`
- `[]` (empty array)
- `{}` (empty object)
- `''` (empty string, or a string containing only newlines and carriage returns)

All other values are truthy. In particular, `semver` values are always truthy regardless of their version number.
