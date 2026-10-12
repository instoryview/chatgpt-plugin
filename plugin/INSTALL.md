# Instoryview Plugin Preview 0.1.0

This download is a local testing package. It is not a listing in the public ChatGPT / Codex Plugins Directory. Universal directory publication requires OpenAI review.

Extract `instoryview-plugin-0.1.0.zip`. The extracted `instoryview-plugin/` directory is a self-contained local marketplace with `.agents/plugins/marketplace.json` and `plugin/`. With a supported Codex CLI, register that extracted marketplace:

```bash
codex plugin marketplace add /absolute/path/to/instoryview-plugin
```

Use the supported ChatGPT desktop plugin browser to select the **Instoryview Preview** marketplace, install Instoryview, and connect your account through OAuth. Local marketplace availability varies by client and workspace policy. Restart or refresh the desktop app if it does not discover the new source. Installation and successful OAuth connection are separate steps.

For ChatGPT preview without a local marketplace, open the Plugins page and use **Add custom MCP server** with `https://instoryview.com/mcp` and OAuth. This tests the server connection; it does not install this ZIP or create a public listing. OAuth discovery and Dynamic Client Registration select connection details. Read scope is `data:read`. Paid online lookup requires separately enabling `data:fetch`, plus an explicit budget for each logical request.

Ask “Show my tracked accounts” or “Show alice's available followers.” Existing-data reads do not consume new collection credits. A missing snapshot does not authorize a paid lookup. For paid collection, say the target, list, and maximum credits explicitly. The bundle contains no credential, client secret, or arbitrary registered connector ID.

The standalone Skill and this Plugin's Skill are generated from the same source. To update, replace this extracted release with a newer version, refresh the marketplace, and review host permissions. Uninstalling the Plugin does not necessarily revoke a separately established MCP authorization: revoke the connection in Instoryview's developer settings when needed.

Official package format and local marketplace instructions: https://developers.openai.com/plugins/build/plugins
