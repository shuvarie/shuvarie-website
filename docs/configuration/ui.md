---
layout: page
title: Interface & themes
parent: Configuration
nav_order: 2
permalink: /docs/configuration/ui/
---

## ui

| Key | Default | Meaning |
| ----- | --------- | --------- |
| `frame-rate` | `60` | TUI frame-rate cap; `0` uncapped |
| `sidebar` | `auto` | `auto` (expanded when the terminal is ≥ 80 cols), `expanded` or `collapsed` |
| `copy-on-select` | `#false` | Copy text automatically when selected with the mouse |
| `theme` | built-in Faerun | Name of a theme from `themes`/`themes.d` |

## themes

Shuvarie ships with **Faerun** (dark, the default) and its light variant.
Set one with `ui { theme "Name" }`; when a name has both variants, the one
matching the terminal's mode is chosen. Define themes in `themes { … }` or
drop files into `themes.d/`; unset roles keep their Faerun values:

```kdl
themes {
    theme name="Midnight" mode="dark" {
        bg "#121216"
        accent "#d4af5f"
    }
    theme name="Midnight" variant="light" mode="light" {
        bg "#fafafa"
        accent "#8a6d1f"
    }
}
```

Colors accept `#rgb`, `#rrggbb` or bare `rrggbb`. Available roles: `bg`,
`surface`, `surface-focused`, `overlay`, `accent`, `accent-bg`, `selection`,
`text`, `text-dim`, `text-muted`, `prompt-bg`, `running-bg`, `success-bg`,
`warning-bg`, `error-bg`, `diff-add-bg`, `diff-add-emph-bg`, `diff-del-bg`,
`diff-del-emph-bg`, `success`, `warning`, `error`.
