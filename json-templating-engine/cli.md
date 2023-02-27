---
layout: page
parent: JSON Templating Engine
title: CLI options
nav_order: 5
---

# CLI options

## Global options

 - `--debug` - Enables debug mode. In debug mode, the engine will print extra information to the console.
 - `--silent` - Reduces the amount of information printed to the console. This flag will have no effect when `--debug` is enabled.
 - `--minify` - Minifies the output. 
 - `--scope` - Adds a file or directory to the scope. This option can be used multiple times.
 - `--cache-dir` - Sets the cache directory. 
 - `--seed` - Sets the seed for random number generator. 

## `compile` action

This action will compile templates and save the results to the output directory.

Example:
```
jsonte compile --out ./result ./src
```

 - `--out` - Sets the output directory. 
 - `--include` - Adds a glob pattern for a file or a directory to the include list. This option can be used multiple times. This list has a higher priority than the exclude list.
 - `--exclude` - Adds a glob pattern for a file or a directory to the exclude list. This option can be used multiple times.
 - `--remove-src` - Removes the source templates after compilation. Flag used mainly for Regolith filter.

## `eval` action

This action will evaluate an expression and print the result to the console. If no expression is provided, the engine will start a REPL.

Example:
```
jsonte eval "pi()"
```

## `version` action

This action will print the version of the engine to the console.

## `ipc` action

This action will start an IPC server. The server will listen for requests on the named pipe. 

Example:
```
jsonte ipc
```

 - `--ipc-name` - Sets the name of the named pipe. Defaults to `jsonte`.