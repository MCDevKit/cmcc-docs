---
layout: page
parent: JSON Templating Engine
title: Merge operations
nav_order: 5
---

# Merge Operations

Merging operations involve combining two objects or arrays, and you can control the behavior of the result by using different techniques.

## Merging Objects

When merging two objects, a new object is created, containing the keys of both original objects. If both objects share a key with a primitive value, the value from the first object is used.

Consider the following `test` module for object examples:

```json
{
    "$module": "test",
    "$template": {
        "test": {
            "a": 1,
            "b": 2
        }
    }
}
```

### Basic Object Merging

```json
{
    "$extend": "test",
    "$template": {
        "test": {
            "b": 3,
            "c": 4
        }
    }
}
```

Result:

```json
{
    "test": {
        "a": 1,
        "b": 3,
        "c": 4
    }
}
```

### Replacing Values

Add a `$` prefix to the key to replace the value of the key instead of merging it.

```json
{
    "$extend": "test",
    "$template": {
        "$test": {
            "b": 3,
            "c": 4
        }
    }
}
```

Result:

```json
{
    "test": {
        "b": 3,
        "c": 4
    }
}
```

### Removing Keys

Set a key's value to `null` to remove it from an object.

```json
{
    "$extend": "test",
    "$template": {
        "test": {
            "b": null
        }
    }
}
```

Result:

```json
{
    "test": {
        "a": 1
    }
}
```

## Merging Arrays

When merging two arrays, a new array is created, containing elements from both original arrays.

Consider the following `test` module for array examples:

```json
{
    "$module": "test",
    "$template": {
        "test": [1, 2]
    }
}
```

### Basic Array Merging

```json
{
    "$extend": "test",
    "$template": {
        "test": [3, 4]
    }
}
```

Result:

```json
{
    "test": [1, 2, 3, 4]
}
```

### Replacing Values

Add a `$` prefix to the key to replace the value of the key instead of merging it.

```json
{
    "$extend": "test",
    "$template": {
        "$test": [3, 4]
    }
}
```

Result:

```json
{
    "test": [3, 4]
}
```

### Prepending Values

Add a `^` prefix to the key to prepend the value of the key instead of appending it.

```json
{
    "$extend": "test",
    "$template": {
        "^test": [3, 4]
    }
}
```

Result:

```json
{
    "test": [3, 4, 1, 2]
}
```