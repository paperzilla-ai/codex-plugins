# Paperzilla Codex Plugins

Codex plugin marketplace for Paperzilla.

## Install

Add this marketplace to Codex:

```sh
codex plugin marketplace add paperzilla-ai/codex-plugins
```

Then open the Codex plugin directory, choose the Paperzilla marketplace, and install the Paperzilla plugin.

## Authentication

Generate a Paperzilla MCP key in the Paperzilla app, then expose it before starting Codex:

```sh
export PAPERZILLA_MCP_KEY="pzmcp_..."
```

The Paperzilla plugin uses that key to connect Codex to:

```text
https://paperzilla.ai/api/mcp
```

## Contents

- `.agents/plugins/marketplace.json`: Codex marketplace catalog.
- `plugins/paperzilla`: Paperzilla plugin package and MCP server config.
