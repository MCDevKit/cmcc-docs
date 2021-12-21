---
layout: page
parent: Tutorials
grand_parent: CommandLang
title: Using with Regolith
---

# What is Regolith

Regolith is an Add-on Compiler for the Bedrock Edition of Minecraft. 

Steps to install are on the [Regolith website](https://bedrock-oss.github.io/regolith/)

## Project setup

Since Regolith takes the role of the compiler, we will initialize it using `regolith` command.

```shell
regolith init
```

After that we need to set up the project structure.

```shell
# Create folder for JSON Templating Engine data
mkdir packs/data/json_templating_engine
# Create folder for CommandLang source code
mkdir packs/data/command_lang
```

## Configuration

The next step is to edit `config.json` file to add JSON Templating Engine and CommandLang as filters to the Regolith.

**This step assumes, that you already properly installed CommandLang and added it to the path.**

```json
{
  "name": "name",
  "author": "author",
  "packs": {
    "behaviorPack": "./packs/BP",
    "resourcePack": "./packs/RP"
  },
  "regolith": {
    "profiles": {
      "dev": {
        "filters": [
          // We need to add JSON Templating Engine separately, because CommandLang as filter will only take care of .mcc files
          {
            "url": "github.com/MCDevKit/regolith-library/json_templating_engine"
          },
          {
            "runWith": "shell",
            "command": "cmcc",
            "arguments": [
              "regolith",
              "--bp-dir",
              "./BP",
              "--data-dir",
              "./data/json_templating_engine",
              "--source-dir",
              "./data/command_lang",
              "--no-ansi"
            ]
          }
        ],
        "export": {
          "target": "development"
        },
        "dataPath": "./packs/data"
      }
    }
  }
}
```

## Adding required files

CommandLang itself requires only one file to be present, which is `packs/data/command_lang/main.mcc`.

```
public func start() {
  // Your code here
}

public func update() {
  // Your code here
}
```

## Installing filters

```shell
regolith install
regolith unlock
```

## Running the compiler

```shell
regolith run
```