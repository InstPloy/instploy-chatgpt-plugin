---
name: instploy-mcp
description: Connect and use InstPloy MCP in ChatGPT. When the user enables InstPloy, says connect InstPloy, or pastes instploy url/Authorization JSON, guide them through ChatGPT Developer mode MCP registration, then use InstPloy tools.
---

# InstPloy MCP (ChatGPT)

## First-time / reconnect

If InstPloy tools are missing, failing auth, or the user wants to connect:

1. Ask them to paste JSON like:

```json
"instploy": {
  "url": "https://YOUR_INSTANCE.instploy.com/instploy/manager/mcp",
  "headers": {
    "Authorization": "Bearer YOUR_TOKEN_HERE"
  }
}
```

2. Parse `url` and Bearer token (strip the `Bearer ` prefix if present)
3. Guide them to connect in ChatGPT:

   - Settings → Security and login → turn on **Developer mode**
   - Open **Plugins** → press **+**
   - Add MCP URL + Bearer token from the pasted JSON
   - Install / enable the **InstPloy** plugin
   - Start a **new chat** and confirm InstPloy tools appear

Accept pasted JSON shapes:

- The `instploy` object only
- `{ "instploy": { ... } }`
- `{ "mcpServers": { "instploy": { ... } } }`

Never invent URL or token values. Never echo the full token — mask it (first 8 chars + `…`).
Do not write Cursor `~/.cursor/mcp.json` from this ChatGPT plugin.

## After connected

- Prefer InstPloy MCP tools for remote workspace, Odoo install/upgrade, terminals, and deploy tasks
- Confirm the target instance before restart/upgrade/delete
- Never commit Bearer tokens to a repo
