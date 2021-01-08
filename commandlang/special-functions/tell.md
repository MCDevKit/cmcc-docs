---
layout: page
parent: Special Functions
grand_parent: CommandLang
title: tell
---

# tell

Compiles to `tellraw` command.

## Usage

```
tell(<target>, <message>);
```

### Arguments

* `target` - who should see the message. This argument accepts a raw selector as well as entity context.
* `message` - message to display. It supports string concatenation with defined fields.

## Example

```
define val;

func showVal(recipient:context) {
    recipient.val = 15;
    tell(recipient, "The value of val is " + recipient.val);
}
```