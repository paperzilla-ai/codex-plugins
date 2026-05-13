# Paperzilla Codex Plugin

This plugin connects Codex to the Paperzilla MCP server at:

```text
https://paperzilla.ai/api/mcp
```

The server is read-oriented and exposes Paperzilla project, feed, search, Atom URL, paper detail, and paper markdown tools.

## Authentication

Generate a Paperzilla MCP key from the Paperzilla app, then expose it to Codex before starting a session:

```sh
export PAPERZILLA_MCP_KEY="pzmcp_..."
```

The plugin reads that value through `bearer_token_env_var` and sends it as the HTTP bearer token for MCP requests.

## Included MCP Server

```json
{
  "paperzilla": {
    "type": "http",
    "url": "https://paperzilla.ai/api/mcp",
    "bearer_token_env_var": "PAPERZILLA_MCP_KEY"
  }
}
```

More setup context: https://docs.paperzilla.ai/guides/mcp
