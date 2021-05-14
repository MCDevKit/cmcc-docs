---
layout: page
parent: Special Functions
grand_parent: CommandLang
title: summon
---

# summon

Summons an entity and returns its context. Uses the same parameter order as `/summon` command

## Usage

```
context result = summon(<entity type>, [spawn pos], [spawn event] [name tag]);
```

```
context result = summon(<entity type>, <name tag> [spawn pos]);
```

### Arguments

* `entity type` - entity type to summon.
* `spawn pos` - spawn position.
* `spawn event` - event to execute on spawned entity.
* `name tag` - name of the entity.

## Example

```
func testParse() {
    context pig = summon("pig");
}
```