---
layout: page
title: Install
permalink: /docs/install/
nav_order: 1
---

Shuvarie ships as a single binary, `shuvarie`. Install it with Nix or build
it with a Rust toolchain — both give you the same program.

## Requirements

- A terminal. Shuvarie is a TUI — it runs entirely inside your terminal.
- One LLM provider to talk to: a local [Ollama](https://ollama.com), or an
  API key for OpenAI, Anthropic, Google, OpenRouter, Azure, AWS Bedrock,
  Vercel and more. You pick the provider on first launch.

## Install with Nix

With [Nix](https://nixos.org) (flakes enabled), straight from GitHub:

```sh
nix run github:shuvarie/shuvarie              # try it
nix profile install github:shuvarie/shuvarie  # keep it
```

Or from a checkout of the repository:

```sh
nix run .              # try it
nix profile install .  # keep it
nix develop            # toolchain shell (rustc, cargo, clippy, rustfmt, rust-analyzer)
```

The flake builds for `x86_64-linux`, `aarch64-linux`, `x86_64-darwin` and
`aarch64-darwin`. The first invocation builds the crate locally, which takes
a few minutes; later runs are instant.

## Build with Cargo

From a checkout of the repository, with a Rust toolchain
([rustup](https://rustup.rs) provides one):

```sh
cargo install --path .
```

## First run

`cd` into a project directory and run `shuvarie`. Two things happen the
first time:

1. **Provider setup.** With no LLM provider configured, Shuvarie opens a
   welcome screen. Press <kbd>Enter</kbd> to open the add-provider form —
   pick a provider kind, give it a name, and paste an API key (local Ollama
   needs none). This is written to
   `~/.config/shuvarie/connections.kdl`.
2. **Workspace trust.** Shuvarie scans the project for agent instructions
   (`AGENTS.md`, `CLAUDE.md`), skills and config files, and asks what it may
   load. Confirm with <kbd>Enter</kbd>, or trim the checkboxes with
   <kbd>Space</kbd> first. See
   [Usage → Workspace trust](/docs/usage/trust/).

That's it — type a prompt and start working. See
[Usage](/docs/usage/) for the day-to-day flow and
[Configuration](/docs/configuration/) for every setting.
