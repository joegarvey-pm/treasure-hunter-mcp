# Treasure Hunter MCP

A read-only [Model Context Protocol](https://modelcontextprotocol.io) server for [Treasure Hunter](https://www.treasurehunter.show) — a directory of card shows, TCG conventions, comic conventions, and estate sales across the US.

This is a **manifest-only** repository. It contains no application source code — Treasure Hunter's main codebase is private. This repo exists so directories and marketplaces that discover MCP servers by scanning a public GitHub repository (README, license, manifest files) have somewhere to point. The MCP server itself runs at the URL below; nothing in this repo is executed or deployed from here.

## Server

- **Endpoint:** `https://www.treasurehunter.show/api/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** none required
- **Docs:** [`llms-full.txt`](https://www.treasurehunter.show/llms-full.txt) · [`/ai`](https://www.treasurehunter.show/ai)
- **Privacy policy:** [`/privacy`](https://www.treasurehunter.show/privacy)

## Tools

| Tool | Description |
|---|---|
| `search_shows` | Search card shows, conventions, and estate sales by location, date range, and event type. |
| `get_show_details` | Look up full details for a specific event by its slug or ID. |
| `get_show_stats` | Summary statistics about the events currently tracked. |

## Adding this server to a client

```json
{
  "mcpServers": {
    "treasure-hunter": {
      "type": "streamable-http",
      "url": "https://www.treasurehunter.show/api/mcp"
    }
  }
}
```

See [`mcp.json`](./mcp.json) in this repo for the same configuration, and [`llms-full.txt`](https://www.treasurehunter.show/llms-full.txt) for full query documentation.

## License

MIT — see [`LICENSE`](./LICENSE). This license covers the manifest files in this repository only; it does not apply to Treasure Hunter's main application, which is closed source.
