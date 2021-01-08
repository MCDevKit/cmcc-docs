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

## Example

```
@Query(query="query.is_alive",id="minecraft:player")
define fieldName;
```