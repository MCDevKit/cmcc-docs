---
layout: page
parent: Annotations
grand_parent: CommandLang
title: Query
---

# Query

This annotation binds a boolean value from Molang query to a field. 

***This annotation requires an entity behavior pack definition present in project in order to inject the animation controller.***

### Arguments

* `query` - Molang query.
* `id` - entity identifier.
* `range` - (optional) an array of integers, that the value can have. This is a JSON Templating Engine language expression.

## Example

```
@Query(query="query.health",id="minecraft:player", range="0..20")
define playerHealth;
```