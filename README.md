# Instoryview for ChatGPT and Codex (preview)

**Connect ChatGPT, Codex and other MCP-capable assistants to [Instoryview](https://instoryview.com), an Instagram follower and following tracker.** Ask about the accounts you track, their retained follower and following snapshots and the changes Instoryview has detected, and get answers that state when the data was observed and how complete it is.

> **Preview.** This Plugin is not yet listed in a public Plugin Directory. You can install it locally, or connect the MCP server directly (below), which works without the Plugin.

## Connect over MCP (OAuth)

Remote MCP endpoint: `https://instoryview.com/mcp`

1. In your client's connector or MCP settings, add the URL and choose **OAuth**.
2. Sign in on Instoryview's authorization page and review the permissions.

`data:read` covers your tracked accounts, follower and following lists and detected changes. Tick **Also allow online queries** if the assistant should be able to look up public accounts (`data:fetch`); every online query then needs an explicit credit budget. Many clients cannot request more permission later, so reconnect to change it.

## Install the Plugin locally

```bash
git clone https://github.com/instoryview/chatgpt-plugin
codex plugin marketplace add ./chatgpt-plugin
```

Then choose **Instoryview Preview** in the Plugins browser, install it and connect through OAuth. Support depends on your client and workspace policy. See [`plugin/INSTALL.md`](plugin/INSTALL.md).

## Ask naturally

- "Which accounts am I tracking?"
- "Show alice's last available followers."
- "What changes did you detect for alice in the last seven days?"
- "Query bob's public followers online, at most 2 credits."

## MCP tools

| Tool | What it does |
|---|---|
| `list_tracking` | Your tracked accounts |
| `get_account` | An account's existing profile and totals |
| `list_followers` / `list_following` | Available follower or following list, one page |
| `get_account_changes` | Detected changes in a date range |
| `query_public_account` | Budgeted online lookup of a public account (needs `data:fetch` and `maxCredits`) |

## What to know

- Reading existing data never starts a scan and spends no collection credits.
- Instagram does not publish follow timestamps: Instoryview reports when a change was *detected*, not when it happened.
- A page or snapshot can cover only part of an Instagram list; the assistant reports `coverage` and warnings.
- No Instagram password is ever requested. The bundle contains no credentials.

## Links

[Plugin docs](https://instoryview.com/docs/plugins) · [Agent Skill](https://github.com/instoryview/skill) · [CLI](https://github.com/instoryview/cli) · [Open API](https://instoryview.com/docs/reference) · [Privacy](https://instoryview.com/privacy) · [Terms](https://instoryview.com/terms) · support@instoryview.com
