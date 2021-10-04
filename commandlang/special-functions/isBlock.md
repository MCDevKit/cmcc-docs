---
layout: page
parent: Special Functions
grand_parent: CommandLang
title: isBlock
---

# isBlock

Returns whether a block exists at the specified coordinates. 

## Usage

```
let result = isBlock(<location>, <block type>, [block data]);
```

### Arguments

* `location` - location of the block to check.
* `block type` - block type.
* `block data` - block data value. If no data is specified, `-1` is used instead.

## Example

```
func testIsBlock() {
    if (isBlock("0 5 0", "dirt", 0)) {
        >>say at coords (0 5 0} there is dirt
    }
}
```