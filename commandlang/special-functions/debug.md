---
layout: page
parent: Special Functions
grand_parent: CommandLang
title: debug
---

# debug

Compiles to `tellraw` command sent to every player. It's a quick function for debugging.

## Usage

```
debug(<message>);
```

### Arguments

* `message` - message to display. It supports string concatenation with defined fields.

## Example

```
define val;

func showVal(recipient:context) {
    recipient.val = 15;
    debug("The value of val is " + recipient.val);
}
```