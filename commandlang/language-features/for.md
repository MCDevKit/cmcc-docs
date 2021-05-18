---
layout: page
parent: Language Features
grand_parent: CommandLang
title: for
---

# for

Use the `for` statement to execute a code block for every entity in selector or entity context. 
It's shorthand for `execute` command.

## Usage

Normal for:
```
for (@a) {
    >>say I'm a player
}
```
```
context players = @a;
for (players) {
    >>say I'm a player
}
```

For with custom parameters:
```
for (@p "0 5 0") {
    >>say I'm the closest player to coords 0 5 0
}
```
This kind of for is compiled into `execute @p 0 5 0`. 
This means, that in the same way, you can use other `execute` command parameters like `detect`.
