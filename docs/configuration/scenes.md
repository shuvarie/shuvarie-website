---
layout: page
title: Scenes
parent: Configuration
nav_order: 7
permalink: /docs/configuration/scenes/
---

A *scene* is the agent's mission profile: its system prompts, sub-agents and
tool gates. The built-in scene, **Default**, is plain coding behavior.

```kdl
scenes {
    default "Plan"  // scene used for new sessions
    scene name="Plan" {
        description "Read and plan before touching code"
        system-prompts { prelude "Think before you act." }
        tools {
            ask-all
            tool "edit_file" { disabled #true }
        }
    }
}
```

Scene fields: `description`, `subagents` (per-sub-agent overrides),
`system-prompts` (`prelude`, `interlude`, `before-each`/`after-each` turn
hooks) and `tools` (`enable-all`/`ask-all`/`disable-all` plus per-tool
`disabled`/`ask`). `thinking #true` is reserved for future use. Switch
scenes live with [`/scene`](/docs/usage/commands/).
