---
layout: page
parent: JSON Templating Engine
title: CLI options
nav_order: 5
---

# CLI Options

This documentation provides an overview of the various command-line interface (CLI) options available for the JSONTE tool. These options can be divided into global options and action-specific options.

## Global Options

These options can be used with any action:

- `--debug`: Enable debug mode. When active, the engine prints additional information to the console.
- `--silent`: Suppress console output. This flag is ignored if `--debug` is enabled.
- `--minify`: Minify the output.
- `--scope`: Add a file or directory to the scope. Can be used multiple times.
- `--cache-dir`: Specify the cache directory.
- `--seed`: Set the seed for the random number generator.

## Actions

### `compile`

The `compile` action compiles templates and saves the results to the output directory.

**Usage:**

```sh
jsonte compile --out ./result ./src
```

**Options:**

- `--out`: Specify the output directory.
- `--include`: Add a file or directory to the include list using a glob pattern. Can be used multiple times. Takes precedence over the exclude list.
- `--exclude`: Add a file or directory to the exclude list using a glob pattern. Can be used multiple times.
- `--remove-src`: Remove source templates after compilation. Primarily used for the Regolith filter.

### `eval`

The `eval` action evaluates an expression and prints the result to the console. If no expression is provided, the engine starts a REPL.

**Usage:**

```sh
jsonte eval "pi()"
```

### `version`

The `version` action displays the engine version in the console.

### `ipc`

The `ipc` action initiates an Inter-Process Communication (IPC) server. The server listens for requests on the named pipe.

**Usage:**

```sh
jsonte ipc
```

**Options:**

- `--ipc-name`: Set the named pipe's name. Defaults to `jsonte`.