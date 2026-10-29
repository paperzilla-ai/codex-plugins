# Paperzilla Codex Plugin

This plugin connects Codex to the Paperzilla MCP server at:

```text
https://paperzilla.ai/api/mcp
```

The server exposes eleven tools for public digests, catalog papers, owned projects, and feeds. Reading Markdown never queues work; requesting generation is a separate action.

## Authentication

Connect your Paperzilla account through the client's OAuth sign-in flow. The server URL is `https://paperzilla.ai/api/mcp`. Review the requested permissions before allowing access.

Every authenticated account can read public digests and catalog papers without a project. Owned projects add personalized feeds. Requesting Markdown processing is a separate write action. No project edits, feedback writes, or paper imports are exposed.

This replacement retires API keys and old tool names. Remove old connection credentials and reconnect with OAuth. Manage or revoke connections at [Connect AI clients](https://paperzilla.ai/ai-connections). See [setup, permissions, and processing states](https://docs.paperzilla.ai/guides/mcp).

## Included MCP Server

```json
{
  "mcpServers": {
    "paperzilla": {
      "type": "http",
      "url": "https://paperzilla.ai/api/mcp",
      "enabled_tools": [
        "account_status",
        "projects_list",
        "projects_get",
        "feed_get",
        "feed_search",
        "public_digests_search",
        "public_digest_issues_list",
        "public_digest_get",
        "paper_get",
        "paper_markdown_get",
        "paper_markdown_request"
      ],
      "required": false,
      "tool_timeout_sec": 90
    }
  }
}
```

More setup context: https://docs.paperzilla.ai/guides/mcp
