---
layout: page
parent: Annotations
grand_parent: CommandLang
title: OnQueryChange
---

# OnQueryChange

This annotation executes a function every time the value from Molang query changes. 

***This annotation requires an entity behavior pack definition present in project in order to inject the animation controller.***

### Arguments

* `query` - Molang query.
* `id` - entity identifier.

## Example

```
@OnQueryChange(query="query.health",id="minecraft:player")
func healthChanged() {
    >>say My health changed!
}
```