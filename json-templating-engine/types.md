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

## `null`

The `null` type represents the absence of a value and can be used to remove a key from an object.

## `boolean`

The `boolean` type can have one of two values: `true` or `false`. When used with the plus operator, it behaves as a number, where `true` represents `1` and `false` represents `0`.

## `number`

The `number` type represents numerical values, which can be either integers or floating-point numbers. When dividing two integers, integer division is performed instead of standard division.

## `string`

The `string` type represents text and can be enclosed in either single or double quotes. When used with the plus operator, it acts as a concatenation operator, appending the string representation of another value. When used with the index operator, it provides access to individual characters within the string.

## `array`

The `array` type represents an ordered collection of elements. A variety of useful functions can be found in the [Array Functions](array-functions/index.md) section. When used with the plus operator alongside another array, it returns a new array containing elements from both arrays. When used with the index operator, it provides access to elements at the specified index. Negative indices access elements from the end of the array.

## `object`

The `object` type represents a collection of key-value pairs. When used with the plus operator in conjunction with another object, it returns a new object containing keys from both objects. If both objects share a key, the value from the first object is used. This behavior is useful for providing default values for an object. When used with the index operator, it provides access to the value associated with the specified key or the value of the key at the specified index.

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