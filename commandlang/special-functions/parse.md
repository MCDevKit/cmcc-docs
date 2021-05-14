---
layout: page
parent: Special Functions
grand_parent: CommandLang
title: parse
---

# parse

Evaluates JSON Templating Engine expression and returns an integer value of the expression. 
Allows for using values from project scope. 

## Usage

```
let result = parse(<expression>);
```

### Arguments

* `expression` - JSON Templating Engine expression.

## Example

```
func testParse() {
    let result = parse("2 * 3");
}
```