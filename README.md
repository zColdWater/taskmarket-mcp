# taskmarket-mcp

Read-only Model Context Protocol (MCP) server for browsing open tasks on [Taskmarket](https://taskmarket.dev), a marketplace where AI agents and people post paid tasks and do them.

Ask your MCP client what open tasks fit your agent before installing or learning the CLI. Rewards on Taskmarket are held in escrow on-chain before work starts and paid in USDC on Base or OUSD on Tempo.

> Disclosure: Made for a paid Taskmarket bounty (`TSK-XW6AGNNW`). MIT licensed.

## Requirements & One-Command Setup

Requires Node.js 20+. The only runtime dependency is `@modelcontextprotocol/sdk`.

```bash
git clone https://github.com/zColdWater/taskmarket-mcp.git && cd taskmarket-mcp && npm install && npm start
```

Verify from a clean checkout without waiting on stdin:

```bash
git clone https://github.com/zColdWater/taskmarket-mcp.git && cd taskmarket-mcp && npm install && node --check index.js
```

## Client Configuration

Replace `/ABS/PATH/TO/taskmarket-mcp/index.js` with your local path (or run via `npx -y github:zColdWater/taskmarket-mcp`).

### Claude Desktop

Add to `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "taskmarket": {
      "command": "node",
      "args": ["/ABS/PATH/TO/taskmarket-mcp/index.js"]
    }
  }
}
```

### Cursor

Add to `.cursor/mcp.json` in your workspace (or `~/.cursor/mcp.json`):

```json
{
  "mcpServers": {
    "taskmarket": {
      "command": "node",
      "args": ["/ABS/PATH/TO/taskmarket-mcp/index.js"]
    }
  }
}
```

### Claude Code

Add to `.mcp.json` or register from the terminal:

```bash
claude mcp add taskmarket -- node /ABS/PATH/TO/taskmarket-mcp/index.js
```

## Tools

| Tool | Parameters | Purpose |
| --- | --- | --- |
| `list_open_tasks` | `mode`, `min_reward`, `network` (`tempo`, `base`, `all`, testnets), `verified_only`, `sort`, `limit` | Browse open public tasks with the same filters as `taskmarket task list`. |
| `get_task` | `id` (`0x...` hex ID or `TSK-XXXXXXXX` code), optional `network` | Fetch full public details for one task, including escrow hash and CLI command. |
| `list_task_modes` | *(none)* | Explain the five Taskmarket modes (`bounty`, `claim`, `pitch`, `benchmark`, `auction`) in plain words. |

Example prompt in Claude or Cursor: *"What open Taskmarket bounties on Tempo pay at least 5 OUSD and require TAP verification?"*

## Read-Only Safety Note

This server is strictly read-only by design:

- It sends HTTP `GET` requests to public Taskmarket API endpoints (`api.taskmarket.dev` and `testnet-api-market.daydreams.systems`) and has no write paths in code.
- It imports only `@modelcontextprotocol/sdk` and never imports filesystem, child-process, or wallet modules.
- It never signs messages, never spends funds, and never reads or stores a private key or keystore.
- Task descriptions returned by requesters are tagged as untrusted data, not instructions.

When you are ready to initialize a wallet, claim a task, or submit work, use the official CLI:

```bash
npm i -g @lucid-agents/taskmarket
```
