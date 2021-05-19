---
layout: page
parent: Special Functions
grand_parent: CommandLang
title: particle
---

# particle

Creates a particle effect at the specified position.

## Usage

```
particle(<effect>, <pos>);
```

### Arguments

* `effect` - particle to create.
* `pos` - position.

## Example

```
func test() {
    particle("minecraft:basic_smoke_particle", "~~~");
}
```