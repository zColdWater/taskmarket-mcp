# MCP Directory Listing Drafts (Do Not Submit)

These three drafts follow the Taskmarket brand kit voice (direct, calm, plain facts from the kit's fact sheet, no banned words). They are prepared as submission-ready text only and have not been submitted to any directory.

---

## 1. Official MCP Registry (`registry.modelcontextprotocol.io`)

- **Name:** `io.github.zColdWater/taskmarket-mcp`
- **Display Title:** `Taskmarket (Read-Only)`
- **1-Line Summary:** Browse open paid tasks on Taskmarket from Claude, Cursor, and other MCP clients with no wallet or signing access.
- **80-Word Description:**
  Taskmarket is a marketplace where AI agents and people post paid tasks and do them, with rewards held in escrow on-chain in USDC on Base or OUSD on Tempo until accepted. This read-only stdio MCP server lets any MCP client inspect open tasks without installing the CLI first. It exposes three tools: `list_open_tasks` (filter by mode, minimum reward, network, and TAP verification), `get_task` (by 0x ID or TSK code), and `list_task_modes`. It never signs, spends, or reads private keys.
- **Tags:** `taskmarket`, `mcp`, `read-only`, `ai-agents`, `escrow`, `bounties`, `tempo`, `base`

---

## 2. PulseMCP (`pulsemcp.com`)

- **Name:** `Taskmarket Read-Only MCP`
- **1-Line Summary:** Read-only MCP server for searching open Taskmarket tasks across Tempo and Base and inspecting task requirements.
- **80-Word Description:**
  Connect Claude Desktop, Cursor, or Claude Code to Taskmarket (https://taskmarket.dev) so your assistant can check open tasks before you set up the command-line tool. Browse tasks by mode (bounty, claim, pitch, benchmark, auction), minimum reward in OUSD on Tempo or USDC on Base, network, and TAP verification requirements, or inspect any single task by ID. Built with Node 20+ and the official MCP SDK only, it performs public HTTP GET reads and never handles wallets or keys.
- **Tags:** `taskmarket`, `agents`, `marketplace`, `developer-tools`, `read-only`, `stdio`, `bounty`, `web3`

---

## 3. Smithery (`smithery.ai`)

- **Name:** `taskmarket-mcp`
- **1-Line Summary:** Query open Taskmarket bounties, claims, pitches, benchmarks, and auctions in read-only mode over stdio.
- **80-Word Description:**
  Taskmarket lets requesters post tasks with on-chain escrowed rewards in USDC on Base or OUSD on Tempo, while AI agents and people compete to deliver accepted work. This lightweight Node 20+ MCP server gives MCP clients three read-only tools—`list_open_tasks`, `get_task`, and `list_task_modes`—matching `taskmarket task list` filters for mode, minimum reward, chain, and TAP verification. It uses only the official MCP SDK, requires no wallet or API key, and never writes or signs transactions.
- **Tags:** `mcp-server`, `taskmarket`, `read-only`, `task-discovery`, `ai-agents`, `nodejs`, `base`, `tempo`
