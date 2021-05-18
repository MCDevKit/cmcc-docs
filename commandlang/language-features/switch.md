---
layout: page
parent: Language Features
grand_parent: CommandLang
title: switch
---

# switch

Use the `switch` statement to select one of many code blocks to be executed.

Apart from the usual `switch` structure, that can be found in other programming languages, there is also a number of use cases, that will statically generate cases.

## Usage

Normal switch:
```
switch (i) {
    case 0 {
        // Code if i == 0
    }
    case 1 {
        // Code if i == 1
    }
    case 2 {
        // Code if i == 2
    }
}
```

Switch over range:
```
switch (i in 0..10) {
    >>say ${index}
}
```
This kind of switch leaves an index variable ready for templating.

Switch with json by index:
```
switch (i) with "['a', 'b', 'c', 'd']" {
    >>say ${value}
}
```
This kind of switch leaves an index and value variable ready for templating. 
The example above will say 'c', when `i` variable is equal to 2.

Switch with json by value:
```
switch (i) with "[1, 2, 3, 4]" {
    >>say ${value}
}
```
This kind of switch leaves an index and value variable ready for templating. 
The example above will say '2', when `i` variable is equal to 2. 
All values must be valid numbers.

## Example

Scope in `project.json`:
```json
{
  "events": {
    "1": "event1",
    "2": "event2",
    "3": "event3"
  }
}
```
Code:
```
// Using switch with json by value
func triggerEvent1(entity:context, event:int) {
    switch (event) with "keys(events)" by value {
        >>event entity ${@entity} ${events[value]}
    }
}

// Using switch with json by index
func triggerEvent2(entity:context, event:int) {
    switch (event) with "asArray(events)" {
        >>event entity ${@entity} ${asArray(events)[index]}
    }
}

// Using switch over range
func triggerEvent3(entity:context, event:int) {
    switch (event in 1..3) {
        >>event entity ${@entity} event${index}
    }
}

// Using normal switch
func triggerEvent4(entity:context, event:int) {
    switch (event) {
        case 1 {            
            >>event entity ${@entity} event1
        }
        case 2 {            
            >>event entity ${@entity} event2
        }
        case 3 {            
            >>event entity ${@entity} event3
        }
    }
}
```