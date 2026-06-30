# Orcool Studio MCP

A self-service creative engine for app and consumer brands, through one MCP.

**[mcp.orcool.com](https://mcp.orcool.com)** · [get.orcool.com](https://get.orcool.com?utm_source=github-readme&utm_medium=mcp-registry&utm_campaign=mcp-distrib)

No card. No bullshit. Just start.

## What it does

Three live feeds, one tool call.

- **Alerts** -- the move, the morning it happens. A daily ping when a competitor ships new creative, not a week late.
- **Patterns** -- the winning move, plus why. The pattern that is working, its format variants, and why it lands, structured so your agent can use it.
- **Reports** -- the week in your category. What worked and why, ready to drop into a brief or a scoring step.

Sold as **Time-to-Winner**: the days to an ad that clears your KPI gate and holds in rotation. Not video volume.

Speed compounds. Opinions don't.

## Connect

The MCP runs as a remote server. You point your agent at one URL and sign in.

| | |
|---|---|
| **Server URL** | `https://mcp.orcool.com` |
| **Sign-in** | Magic link + a short profile |
| **Cost to start** | Free, no card |

Pick your client below.

### Claude (Desktop & Web)

1. Open **Settings → Connectors** (or **Customize → Connectors**).
2. Click **+ Add custom connector**.
3. Paste `https://mcp.orcool.com` and save.
4. Approve the magic-link sign-in in the browser tab that opens.
5. Back in a chat, open the connectors menu and **enable Orcool for that chat**.

### Claude Code (CLI)

```bash
claude mcp add --transport http orcool https://mcp.orcool.com
```

Then run `claude`, start a session, and approve the sign-in when prompted. Check it loaded with `/mcp`.

### Cursor

1. **Settings → MCP → Add** (or edit `~/.cursor/mcp.json`).
2. Add the server:

```json
{
  "mcpServers": {
    "orcool": {
      "url": "https://mcp.orcool.com"
    }
  }
}
```

3. Reopen Settings → MCP, confirm Orcool shows green, and complete the magic-link sign-in.

### Windsurf

Edit `~/.codeium/windsurf/mcp_config.json`:

```json
{
  "mcpServers": {
    "orcool": {
      "serverUrl": "https://mcp.orcool.com"
    }
  }
}
```

Refresh the MCP panel in Cascade and approve sign-in.

### VS Code (Copilot / Agent mode)

Add to `.vscode/mcp.json` in your workspace, or run **MCP: Add Server** from the command palette:

```json
{
  "servers": {
    "orcool": {
      "type": "http",
      "url": "https://mcp.orcool.com"
    }
  }
}
```

Open the Copilot chat tools picker, enable Orcool, sign in.

### ChatGPT

Custom MCP connectors need **Developer mode**, which is plan-gated. If you have it: **Settings → Connectors → Advanced → Developer mode**, then add `https://mcp.orcool.com`. If you don't see it, use Claude or Cursor instead.

### Any other MCP client

Most clients accept a remote server by URL. The pattern is the same everywhere:

```json
{
  "mcpServers": {
    "orcool": {
      "url": "https://mcp.orcool.com"
    }
  }
}
```

Some clients use a `"type": "http"` (or `"sse"`) field and a `"serverUrl"` key instead of `"url"`. Check your client's MCP docs for the exact key, point it at the URL above, and sign in with the magic link.

## Set it all up in one paste

After the connector is live, paste this into a fresh chat to onboard your brand and get a first concept:

> Connect to Orcool, set up a brand for me, and walk me to my first winning concept. Ask me only what you need: product, the markets I care about, my KPI gate, and one or two competitors. Then pull Alerts and Patterns for my category, propose concepts in a format matrix, and let me approve or kill each one.

A good recurring follow-up, once you're running:

> What's new in my signal feed since last time, and which concept is closest to clearing my KPI gate?

## First win

1. Connect the MCP (above).
2. Onboard your brand: product, markets, KPI gate, a competitor or two.
3. Pull Alerts and Patterns for your category.
4. Pick the angle to test and ship it.
5. Check the Report the following week to see what held.

## FAQ

**Do I need a media buyer or an editor to start?** No. You start solo with the connector and your judgment. Experts plug in where they add the most: approving and killing concepts.

**Is this a video factory?** No. The product is Time-to-Winner, not output volume. One concept that holds beats a hundred that don't.

**What if my client uses Slack or another tool?** The MCP is the workspace. Alerts, Patterns, and Reports land in one place, instead of routing screenshots and briefs through chat.

**Optional plugin.** Bundled connectors and skills live at `github.com/orcool-org/agent-plugin`.

---

Built by Orcool. Questions: [team@orcool.com](mailto:team@orcool.com) · [get.orcool.com](https://get.orcool.com?utm_source=github-readme&utm_medium=mcp-registry&utm_campaign=mcp-distrib)
