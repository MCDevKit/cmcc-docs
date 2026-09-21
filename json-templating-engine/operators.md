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
| `+x`     | Unary plus     | Returns the number unchanged                                              |

There is no `%` operator. Use the `mod(a, b)` function instead.

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

The `: valueIfFalse` part is optional. Without it, the expression returns `null` when the condition is falsy:

```json
{
  "$template": {
    "$comment": "'yes' when enabled is truthy, null otherwise",
    "key": "{{"{{enabled ? 'yes'"}}}}"
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

## Array Slicing

Indexing an array with a range returns a new array with the elements at those indices. Negative indices count from the end of the array. An index outside the array causes an error.

```json
{
  "$template": {
    "$comment": "With list equal to [10, 20, 30, 40], first is [20, 30] and last is [30, 40]",
    "first": "{{"{{=list[1..2]"}}}}",
    "last": "{{"{{=list[-2..-1]"}}}}"
  }
}
```

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
| `-=`     | Subtract and assign             |
| `*=`     | Multiply and assign             |
| `/=`     | Divide and assign               |
| `%=`     | Assign the remainder            |
| `++`     | Increment by one                |
| `--`     | Decrement by one                |

`/=` and `%=` with integers and a divisor of zero produce `NaN`.

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

## `in` Operator

The `in` operator checks whether a value is contained in another value:

- For an object, it checks whether the object has the key.
- For an array, it checks whether the array has the element.
- For a string, it checks whether the string contains the substring.

```json
{
  "$template": {
    "$comment": "All values below are true",
    "hasKey": "{{"{{'x' in {'x': 1}"}}}}",
    "hasElement": "{{"{{20 in [10, 20]"}}}}",
    "hasSubstring": "{{"{{'ell' in 'hello'"}}}}"
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

## Operator Precedence

Operators are evaluated in the order below, from the highest to the lowest precedence. Use parentheses to change the order.

| Operators                                    | Description                                                     |
| -------------------------------------------- | --------------------------------------------------------------- |
| `.`, `?.`, `[]`, `?[]`, `()`, `++`, `--`     | Member access, indexing, function calls, increment, decrement   |
| `-x`, `+x`, `!`                              | Unary minus, unary plus, logical not                            |
| `*`, `/`                                     | Multiplication and division                                     |
| `+`, `-`                                     | Addition and subtraction                                        |
| `..`                                         | Range                                                           |
| `<`, `<=`, `>`, `>=`, `in`                   | Comparison and containment                                      |
| `==`, `!=`                                   | Equality                                                        |
| `&&`                                         | Logical AND                                                     |
| `\|\|`                                       | Logical OR                                                      |
| `??`                                         | Null coalescing                                                 |
| `? :`                                        | Ternary                                                         |
| `=`, `+=`, `-=`, `*=`, `/=`, `%=`            | Assignment                                                      |

For example, `1 < 2 == true` is `true`, because the comparison is evaluated before the equality. `null ?? 1 == 2` is `false`, because `1 == 2` is evaluated before `??`.
