---
layout: page
parent: Annotations
grand_parent: CommandLang
title: OnQuery
---

# OnQuery

This annotation executes a function every time the value from Molang query becomes true. 

***This annotation requires an entity behavior pack definition present in project in order to inject the animation controller.***

### Arguments

* `query` - Molang query.
* `id` - entity identifier.
* `single` - whether this function should run only once per entity.

## Example

```
@OnQuery(query="query.is_alive",id="minecraft:player")
func aliveTrigger() {
    >>say I'm alive!
}
```