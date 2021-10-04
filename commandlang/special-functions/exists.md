---
layout: page
parent: Special Functions
grand_parent: CommandLang
title: exists
---

# exists

Returns whether a scoreboard value exists on the entity. 

## Usage

```
let result = exists(<selector>.<score name>);
```

### Arguments

* `selector` - location of the block to check.
* `score name` - name of the scoreboard value.

## Example

```
func testExists() {
    if (exists(@e[type=pig,c=1].test)) {
        >>say nearest pig has a scoreboard value 'test'
    }
}
```