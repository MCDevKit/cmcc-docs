---
layout: page
parent: JSON Templating Engine
title: Merge operations
nav_order: 5
---

# Merge operations

When merging two objects or arrays, there are different behaviors, that can be used to control the result.

## Merging objects

When merging two objects, the result will be a new object, that will have keys of both objects. If both objects have the same key with a primitive value, the value of the first object will be used.

The following module `test` will be used for all object examples:
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

### Replacing values

We can add a `$` prefix to the key, to replace the value of the key, instead of merging it.

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

Result:

```json
{
    "test": {
        "b": 3,
        "c": 4
    }
}
```

### Removing keys

To remove a key from an object, we can set its value to `null`.

```json
{
    "$extend": "test",
    "$template": {
        "test": {
            "b": null
        }
    }
}

Result:

```json
{
    "test": {
        "a": 1
    }
}
```

## Merging arrays

When merging two arrays, the result will be a new array, that will have elements of both arrays.

The following module `test` will be used for all array examples:
```json
{
    "$module": "test",
    "$template": {
        "test": [1, 2]
    }
}
```

```json
{
    "$extend": "test",
    "$template": {
        "test": [3, 4]
    }
}

Result:

```json
{
    "test": [1, 2, 3, 4]
}
```

### Replacing values

We can add a `$` prefix to the key, to replace the value of the key, instead of merging it.

```json
{
    "$extend": "test",
    "$template": {
        "$test": [3, 4]
    }
}

Result:

```json
{
    "test": [3, 4]
}
```

### Prepending values

We can add a `^` prefix to the key, to prepend the value of the key, instead of appending it.

```json
{
    "$extend": "test",
    "$template": {
        "^test": [3, 4]
    }
}

Result:

```json
{
    "test": [3, 4, 1, 2]
}
```
