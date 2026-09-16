---
layout: default
title: Home
permalink: /
nav_exclude: true
---

<div class="hero">
  <p class="hero-kicker">⚔️⚜️ シュヴァリエ ⚜️⚔️</p>
  <h1>Shuvarie</h1>
  <p class="tagline">The AI coding agent for chivalrous people.</p>
  <div class="btn-row">
    <a class="btn btn-primary" href="{{ "/docs/install/" | relative_url }}">Install</a>
    <a class="btn" href="{{ "/docs/usage/" | relative_url }}">Usage</a>
    <a class="btn" href="{{ "/docs/configuration/" | relative_url }}">Configuration</a>
  </div>
</div>

<img
  class="screenshot"
  src="{{ "/assets/shuvarie-screenshot-demo.png" | relative_url }}"
  alt="Shuvarie — an agentic coding session in the terminal"
/>

An agentic AI pair-programmer that lives in your **terminal**. Shuvarie reads
your code, edits files, runs tools and keeps a forkable history of every
decision — all under explicit, granular permissions you control.

<div class="features">
  <div class="feature">
    <h3>🔌 Bring your own model</h3>
    <p>OpenAI-compatible, Anthropic, Ollama and more — configured in one
    <code>connections.kdl</code>, switchable on the fly with <code>/model</code>.</p>
  </div>
  <div class="feature">
    <h3>🌲 Sessions &amp; forking</h3>
    <p>Every session is a tree. Inspect it with <code>/tree</code>, roll back
    with <code>/undo</code>, replay, and export or import sessions as JSON.</p>
  </div>
  <div class="feature">
    <h3>🧩 Skills</h3>
    <p>Reusable prompts and procedures stored as markdown, invoked straight
    from the prompt as <code>/skill:&lt;name&gt;</code>.</p>
  </div>
  <div class="feature">
    <h3>🎨 Scenes &amp; themes</h3>
    <p>Drop-in <code>scene.d</code> and <code>themes.d</code> files change how
    Shuvarie looks and behaves; switch live with <code>/scene</code> and
    <code>/theme</code>.</p>
  </div>
  <div class="feature">
    <h3>🛡️ Permissions &amp; trust</h3>
    <p>A workspace trust prompt on first run, plus a granular allow/deny
    <code>permissions</code> section — the agent never acts unbound.</p>
  </div>
  <div class="feature">
    <h3>⌨️ Keyboard-first</h3>
    <p>Every action has a keybinding, and every keybinding is configurable
    in <code>config.kdl</code>.</p>
  </div>
</div>

## Try it

```sh
# with Nix (flakes enabled)
nix run github:shuvarie/shuvarie            # try it
nix profile install github:shuvarie/shuvarie  # keep it

# or with a Rust toolchain, from a checkout
cargo install --path .
```

Then read the [Install]({{ "/docs/install/" | relative_url }}),
[Usage]({{ "/docs/usage/" | relative_url }}) and
[Configuration]({{ "/docs/configuration/" | relative_url }}) pages.