---
layout: page
title: Slash commands
parent: Usage
nav_order: 2
permalink: /docs/usage/commands/
---

| Command | Menu label | Description |
| --------- | ----------- | ------------- |
| `/model` | Select model | Pick the active model |
| `/provider` | Add provider | Add a new LLM provider |
| `/sessions` | Switch session | Resume or delete past sessions |
| `/tree` | Session tree | Walk the tree, fork from any node |
| `/scene` | Switch scene | Pick the scene the agent runs under (`/scene <name>`) |
| `/variant` | Select variant | Pick the model's reasoning effort (`/variant HIGH`) |
| `/new` | New session | Start a fresh conversation |
| `/title` | Edit title | Rename the current session (`/title My title`) |
| `/export` | Export session | Write the session to a JSON file (optional path) |
| `/undo` | Undo last turn | Fork before the last prompt |
| `/replay` | Replay last turn | Fork and re-run the last turn |
| `/reload` | Reload skills | Re-discover skills without restarting |
| `/sidebar` | Toggle sidebar | Collapse or expand the sidebar |
| `/quit` | Quit | Exit the program |

Some commands only appear when they apply: `/undo`, `/replay` and `/tree`
need messages in the chat, `/scene` is hidden while a reply is streaming,
and `/title` and `/export` need an active session.

<kbd>Ctrl+M</kbd> opens the same commands as a searchable menu.
