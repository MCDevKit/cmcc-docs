---
layout: default
title: Getting started
nav_order: 0
permalink: /
---

# Getting started with CommandLang

CommandLang is a programming language compiled to Minecraft Bedrock Edition commands. Its aim is to help with designing map logic.

## Installation

* Download CMCC from Downloads page in client panel
* Move it to a folder, where it won't be accidentally removed or moved somewhere else
* Add it to the PATH environment variable
  * Find and open in Start menu 'Edit the system environment variables'
  * Click 'Environment variables' at the bottom
  * Find and click 'Path' variable in the list and click Edit
  * In the edit window, click 'Add' and write full path to the folder, where CMCC is saved
  * Exit all windows by clicking Ok
* Open terminal of choice (Command Line/Powershell/Git Bash/Other) and confirm, that it's working by entering `cmcc` and hitting enter 

## Activation

* Go to [Client Panel](https://cmcc.stirante.com/panel)
* Make sure you have active subscription
* Copy License Key
* Open terminal of choice and type `cmcc activate <license key>`, where `<license key>` should be replaced with what you copied in previous step


## Creating first project

CommandLang aims to be a tool for complete pack creation and thus requires a certain structure of the project. 
To make that easier, there is a simple command, that creates everything required to start coding.

* Open terminal of choice in a folder, where you want to start your project
* Enter `cmcc init <project name> <project description>`
* To verify, that the project has been created properly, enter `cmcc build`

## Setup automatic install

CommandLang offers a way to install project directly to the development packs or specified world. 

* Edit `project.json` file and configure properties under `install`:
  * `save_folder` - name of the folder, where the world we want to install to is (note, that it's the name of the folder, not name of the world. Those usually look like this `Y4daX8R3AAA=`)
  * `install_in_dev` - whether to install the project to development folders (development_behavior_packs and development_resource_packs)
  * `'mojang_folder` - path to the `com.mojang` folder. This is filled by default, but may be incorrect for systems with multiuser setup and so for some, it might be required to manually fix this path.
* Enter in terminal `cmcc install`. This should automatically compile project and copy it to configured location.

## Running CommandLang in a world

* Add both resource pack and behavior pack to the world
* Place Repeating Command Block, set its command to `function main`, delay to 0 and make it 'always active'