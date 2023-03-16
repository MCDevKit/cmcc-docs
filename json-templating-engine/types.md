---
layout: page
parent: JSON Templating Engine
title: Basic types
nav_order: 4
---

# Basic Data Types

JsonTE supports all fundamental data types found in JSON, as well as an additional `semver` type for representing [semantic versioning](https://semver.org/). The basic data types in JsonTE are:
- `null`
- `boolean`
- `number`
- `string`
- `array`
- `object`
- `semver`

## `null`

The `null` type represents the absence of a value and can be used to remove a key from an object.

## `boolean`

The `boolean` type can have one of two values: `true` or `false`. When used with the plus operator, it behaves as a number, where `true` represents `1` and `false` represents `0`.

## `number`

The `number` type represents numerical values, which can be either integers or floating-point numbers. When dividing two integers, integer division is performed instead of standard division.

## `string`

The `string` data type is used to represent textual information and can be enclosed within either single (`'`) or double (`"`) quotes. When the plus (`+`) operator is used with strings, it functions as a concatenation operator, joining the string representation of another value to the original string. The index operator (`[]`) allows access to individual characters within the string by specifying their position.

## `array`

The `array` type is an ordered collection of elements, offering a wide range of functionality to manipulate and process data. To explore the available functions, refer to the [Array Functions](array-functions/index.md) section.

When combining two arrays using the plus (`+`) operator, a new array is created that consists of the elements from both input arrays. For example:

```json
{
  "$template": {
    "array1": [1, 2, 3],
    "array2": [4, 5, 6],
    "combined_array": "{{"{{array1 + array2"}}}}"
  }
}
```

To access individual elements within an array, use the index operator (`[]`). The index is zero-based, meaning the first element is at index `0`. Negative indices allow you to access elements from the end of the array, with `-1` referring to the last element. For example:

```json
{
  "$template": {
    "array": [1, 2, 3, 4, 5],
    "first_element": "{{"{{array[0]"}}}}",
    "last_element": "{{"{{array[-1]"}}}}"
  }
}
```

## `object`

The `object` type represents a collection of key-value pairs, which allows for easy storage and retrieval of data. When you use the plus operator (`+`) to combine two objects, it generates a new object containing keys and their corresponding values from both of the original objects. If the two objects share a common key, the value from the first object takes precedence. This feature is particularly useful for setting default values in an object.

To access a specific value within an object, you can use the index operator (`[]`). By providing the desired key or index within the square brackets, you can quickly retrieve the associated value.

## `semver`

The `semver` type represents a [semantic version](https://semver.org/) and supports all standard comparison operators, including less than and greater than. The individual components of the version can be accessed using the following aliases:

Major version:
- `major`
- `a`
- `x`

Minor version:
- `minor`
- `b`
- `y`

Patch version:
- `patch`
- `c`
- `z`

Refer to the [Semver Functions](semver-functions/index.md) section to learn how to create a `semver` type in JsonTE.