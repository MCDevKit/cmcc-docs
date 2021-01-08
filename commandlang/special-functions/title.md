---
layout: page
parent: Special Functions
grand_parent: CommandLang
title: title
---

# title

Compiles to `titleraw` command.

## Usage

```
title(<target>, <title location>, <message>);
```

### Arguments

* `target` - who should see the message. This argument accepts a raw selector as well as entity context.
* `title location` - valid values are `actionbar`, `subtitle` and `title`
* `message` - message to display. It supports string concatenation with defined fields.

## Example

```
define val;

func showVal(recipient:context) {
    recipient.val = 15;
    title(recipient, actionbar, "The value of val is " + recipient.val);
}
```