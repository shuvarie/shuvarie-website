---
layout: page
title: Tools & integrations
parent: Configuration
nav_order: 5
permalink: /docs/configuration/tools/
---

## tools

The `web-search` tool (exposed to the model as `web_search`) is off until
you point it at a search endpoint:

```kdl
tools {
    web-search {
        enabled #true
        url "https://example.com/search"  // required, must start with http(s)://
        type "ollama"                     // or "to_markdown" (fetch page → markdown)
        headers { Authorization "Bearer $MY_TOKEN" }  // $VAR / ${VAR} expand from the environment
        params type="body-json" {         // or type="query" for GET parameters
            query as="q"                  // tool argument → remote parameter name
        }
    }
}
```

Default `params` when omitted: `ollama` ⇒ POST body with `query as="query"`;
`to_markdown` ⇒ GET query with `query as="q"`.

## shell

```kdl
shell {
    path "/usr/bin/zsh"  // executable for run_shell; absolute, relative, or PATH lookup
}
```

## lsp

```kdl
lsp {
    disabled #false
    servers {
        rust {
            command "rust-analyzer" "..."   // language server command
            extensions "rs"                  // file extensions it serves
            no-auto-start #true              // opt-in only
            root-markers "Cargo.toml"        // files marking a project root
        }
    }
}
```

All fields are optional; the server name is the language it serves.
`lsp.servers` merges key-by-key across config layers.
