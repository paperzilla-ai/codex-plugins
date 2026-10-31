# Paperzilla Codex Plugin

This plugin connects Codex to the Paperzilla MCP server at:

```text
https://paperzilla.ai/api/mcp
```

The server exposes thirteen tools for public digests, catalog papers, owned projects, and feeds. Reading Markdown never queues work; requesting generation is a separate action.

## Authentication

Connect your Paperzilla account through the client's OAuth sign-in flow. The server URL is `https://paperzilla.ai/api/mcp`. Review the requested permissions before allowing access.

Every authenticated account can read public digests and catalog papers without a project. Owned projects add personalized feeds. Requesting Markdown processing and saving or clearing feedback are separate write actions. No project edits or paper imports are exposed.

Feedback requires the explicit `feedback:write` OAuth permission. Use `feedback_set` with the full `project_paper_id` from an owned feed, `vote` (`upvote`, `downvote`, or `star`), and optional `downvote_reason` (`not_relevant` or `low_quality`, only for downvotes). `feedback_clear` removes that item's feedback. Each project has its own rating even when the same canonical paper appears elsewhere. Never infer ratings from a brief's ranking; save feedback only when the user asks.

Existing connections retain their scopes. Refresh the tool list and reconnect with fresh feedback consent to enable writing. If an old dynamic client registration reports `invalid_scope`, remove and re-add the client connection so it can register with the new scope. Keep write tools on approval-required settings; read-only tools may be allowed separately.

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
        "paper_markdown_request",
        "feedback_set",
        "feedback_clear"
      ],
      "required": false,
      "tool_timeout_sec": 90
    }
  }
}
```

More setup context: https://docs.paperzilla.ai/guides/mcp
