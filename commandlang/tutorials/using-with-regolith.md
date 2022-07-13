---
layout: page
parent: Tutorials
grand_parent: CommandLang
title: Using with Regolith
---

# What is Regolith

Regolith is an Add-on Compiler for the Bedrock Edition of Minecraft. 

Steps to install are on the [Regolith website](https://bedrock-oss.github.io/regolith/)

## Prerequisites

Before proceeding, make sure you have CommandLang properly installed and activated. For JSON Templating Engine also the Java 11 or later is required. Instructions are provided [here](https://bedrock-oss.github.io/regolith/docs/java-filters#installing-java)

## Project setup

Since Regolith takes the role of the compiler, we will initialize it using `regolith` command.

```shell
regolith init
```

After that we need to add JSON Templating Engine and CommandLang as filters.

```shell
regolith install github.com/MCDevKit/regolith-library/json_templating_engine
regolith install github.com/MCDevKit/regolith-library/command_lang
```

## Configuration

The next step is to edit `config.json` file to add JSON Templating Engine and CommandLang as filters to the chosen profile. Only relevant fields are shown.

```json
{
  "regolith": {
    "profiles": {
      "default": {
        "filters": [
          {
            "filter": "json_templating_engine"
          },
          {
            "filter": "command_lang"
          }
        ]
      }
    }
  }
}
```

## Unlocking community filters

By default, Regolith blocks running community filters, which means that once per project, you need to unlock it by running this command.

```shell
regolith unlock
```

## Running the compiler

```shell
regolith run
```
