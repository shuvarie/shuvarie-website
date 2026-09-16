---
layout: page
title: Command line & the prompt
parent: Usage
nav_order: 1
permalink: /docs/usage/cli/
---

## Command line

| Invocation | Meaning |
| ------------ | --------- |
| `shuvarie` | Start a new session in the current directory |
| `-c`, `--current` | Resume the most recently updated session |
| `-s`, `--session <UUID>` | Resume a specific session by UUID |
| `-d`, `--dir <DIR>` | Run in another directory (the session database lives there too) |
| `--config <FILE>` | Use an explicit config file, bypassing the workspace-config trust scan |
| `--export-session [FILE]` | Export a session to JSON and exit |
| `--import-session <FILE>` | Import a session JSON snapshot and exit |
| `-h`, `--help` | Show help |
| `-V`, `--version` | Show version |

When you quit, Shuvarie prints the exact command to reopen the session:

```
This session can be reopened with:

  shuvarie -s <session-uuid>
```

## The prompt

- <kbd>Enter</kbd> submits, <kbd>Shift</kbd>+<kbd>Enter</kbd> inserts a
  newline.
- A leading `!` runs the rest of the line as a **local shell command**
  instead of prompting the agent (bash mode).
- A leading `/` or `:` starts a **slash command**
  ([list](/docs/usage/commands/)). Matching is case-insensitive; type the
  trigger twice (`//`) to send a literal slash. An autocomplete menu
  appears as you type.
- `/skill:<name> [args]` expands a
  [skill](/docs/configuration/skills/) into its stored prompt and sends it.
