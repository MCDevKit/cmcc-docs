---
layout: page
parent: JSON Templating Engine
title: Scripting (.jsonte files)
nav_order: 9
---

# Scripting (.jsonte files)

Files with the `.jsonte` extension are executed as scripts before templates are processed. A `.jsonte` script runs against the current scope and can read and write scope variables, making it useful for computing derived values, loading data, or preparing complex structures that would be awkward to express inline in a template.

## Basic Usage

A `.jsonte` script is a sequence of statements, each terminated by a semicolon. The script has full access to all scope variables and built-in functions.

```js
// Set a new scope variable
$scope.greeting = `Hello, ${name}!`;

// Compute a derived value
$scope.itemCount = items.count();
```

## The `$scope` Pseudo-variable

Inside a `.jsonte` script, `$scope` is a proxy to the global scope object. Use it to create new top-level scope variables:

```js
$scope.doubled = value * 2;
$scope.names = items.map(x => x.name);
```

You can also mutate existing scope variables directly by assigning to them, since variables that already exist in the scope carry a reference to their parent:

```js
// If 'settings' is already in scope, this modifies it in-place
settings.debug = true;
```

Script-local variables (e.g. loop counters) are discarded when the script finishes.

## If / Else

```js
if count > 10 {
    $scope.label = 'many';
} else if count > 1 {
    $scope.label = 'some';
} else {
    $scope.label = 'none';
}
```

## For Loop

Iterate over an array with an optional index variable:

```js
for item in items {
    // item is the current element
}

for item, i in items {
    // item is the element, i is the zero-based index
}
```

## While Loop

```js
while condition {
    // body
}
```

## Do-While Loop

```js
do {
    // body
} while condition;
```

## Break and Continue

`break` exits the current loop and `continue` skips to the next iteration:

```js
for item in items {
    if item == null {
        continue;
    }
    if item.id == targetId {
        $scope.found = item;
        break;
    }
}
```

## Return

`return` exits a lambda or block body, optionally producing a value:

```js
$scope.firstEven = items.find(x => {
    if x % 2 == 0 {
        return x;
    }
});
```

At the top level of a `.jsonte` script, `return` exits the script early.

## Variable Assignment

Use `=` to assign to any writable location and `+=` to add-and-assign:

```js
$scope.total = 0;
for item in items {
    $scope.total += item.price;
}
```

## Full Example

```js
// Compute a discounted price list from scope variables
$scope.discounted = items.map(item => {
    return {
        'name': item.name,
        'price': item.price * (1 - discount)
    };
});

if $scope.discounted.count() == 0 {
    $scope.discounted = null;
}
```

After this script runs, the `discounted` variable is available to all templates that share the same scope.
