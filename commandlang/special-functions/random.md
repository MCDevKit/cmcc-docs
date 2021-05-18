---
layout: page
parent: Special Functions
grand_parent: CommandLang
title: random
---

# random

Returns random number between specified min and max values.

## Usage

```
let result = random(<min>, <max>);
```

### Arguments

* `min` - minimum value (inclusive). Must be greater than or equal to -2147483648.
* `max` - maximum value (inclusive). Must be less than or equal to 2147483647.

## Example

```
func test() {
    let rand = random(0, 10000000);
}
```