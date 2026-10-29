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

Every authenticated account can read public digests and catalog papers without a project. Owned projects add personalized feeds. Requesting Markdown processing is a separate write action. No project edits, feedback writes, or paper imports are exposed.

This replacement retires API keys and old tool names. Remove old connection credentials and reconnect with OAuth. Manage or revoke connections at [Connect AI clients](https://paperzilla.ai/ai-connections). See [setup, permissions, and processing states](https://docs.paperzilla.ai/guides/mcp).

## Contents

- `.agents/plugins/marketplace.json`: Codex marketplace catalog.
- `plugins/paperzilla`: Paperzilla plugin package and MCP server config.
