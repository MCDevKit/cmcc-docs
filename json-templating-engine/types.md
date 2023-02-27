---
layout: page
parent: JSON Templating Engine
title: Basic types
nav_order: 4
---

# Basic types

JsonTE supports all basic types, that are supported by JSON, including:
 - `null`
 - `boolean`
 - `number`
 - `string`
 - `array`
 - `object`

Additionally, it has a `semver` type, that is used to represent [semantic versioning](https://semver.org/).

## `null`

`null` is a special type, that represents the absence of a value. It can be used to remove a key from an object.

## `boolean`

`boolean` is a type, that can be either `true` or `false`. When using plus operator, it will act as a number, where `true` is `1` and `false` is `0`.

## `number`

`number` is a type, that represents a number. It can be either an integer or a floating point number. 

## `string`

`string` is a type, that represents a string. It can be either a single-quoted or a double-quoted string. 

When using plus operator, it will act as a concatenation operator and add another value's string representation. 

When using index operator, it will act as a character access operator and return a single character.

## `array`

`array` is a type, that represents an array. It supports a number of useful functions, that can be found in the [Array functions](array-functions/index.md) section.

When using plus operator with another array, it will return a new array, that will have elements of both arrays. 

When using index operator, it will act as an array access operator and return an element at the specified index. Using a negative index will access the element from the end of the array.

## `object`

`object` is a type, that represents an object. 

When using plus operator with another object, it will return a new object, that will have keys of both objects. If both objects have the same key, the value of the first object will be used.
It can be used to provide default values for an object.

When using index operator, it will act as an object access operator and return a value of the specified key or value of the key under specified index.

## `semver`

`semver` is a type, that represents a [semantic version](https://semver.org/). 

All comparison operators can be used with `semver` type including less than and greater than operators.

You can access all parts of the version by using these names:

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

JsonTE contains a function for creating a semver type in the [Semver functions](semver-functions/index.md) section.