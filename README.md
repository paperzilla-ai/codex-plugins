# Paperzilla Codex Plugins

Codex plugin marketplace for Paperzilla.

## Install

Add this marketplace to Codex:

```sh
codex plugin marketplace add paperzilla-ai/codex-plugins
```

Then open the Codex plugin directory, choose the Paperzilla marketplace, and install the Paperzilla plugin.

## Authentication

Connect your Paperzilla account through the client's OAuth sign-in flow. The server URL is `https://paperzilla.ai/api/mcp`. Review the requested permissions before allowing access.

Every authenticated account can read public digests and catalog papers without a project. Owned projects add personalized feeds. Requesting Markdown processing and saving or clearing feedback are separate write actions. No project edits or paper imports are exposed.

Feedback requires the explicit `feedback:write` OAuth permission. Use `feedback_set` with the full `project_paper_id` from an owned feed, `vote` (`upvote`, `downvote`, or `star`), and optional `downvote_reason` (`not_relevant` or `low_quality`, only for downvotes). `feedback_clear` removes that item's feedback. Each project has its own rating even when the same canonical paper appears elsewhere. Never infer ratings from a brief's ranking; save feedback only when the user asks.

Existing connections retain their scopes. Refresh the tool list and reconnect with fresh feedback consent to enable writing. If an old dynamic client registration reports `invalid_scope`, remove and re-add the client connection so it can register with the new scope. Keep write tools on approval-required settings; read-only tools may be allowed separately.

This replacement retires API keys and old tool names. Remove old connection credentials and reconnect with OAuth. Manage or revoke connections at [Connect AI clients](https://paperzilla.ai/ai-connections). See [setup, permissions, and processing states](https://docs.paperzilla.ai/guides/mcp).

## Contents

- `.agents/plugins/marketplace.json`: Codex marketplace catalog.
- `plugins/paperzilla`: Paperzilla plugin package and MCP server config.
