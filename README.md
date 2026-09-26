# InstPloy ChatGPT Plugin

ChatGPT / Codex-only Agent Plugin that connects to InstPloy MCP.

> Cursor users: use the separate package `instploy-cursor-plugin`.

## Your InstPloy JSON

```json
"instploy": {
  "url": "https://YOUR_INSTANCE.instploy.com/instploy/manager/mcp",
  "headers": {
    "Authorization": "Bearer YOUR_TOKEN_HERE"
  }
}
```

## Install on ChatGPT

1. Enable **Developer mode**: Settings → Security and login → Developer mode
2. Register the MCP server: Plugins → **+** → paste InstPloy URL + Bearer token
3. Install this plugin from a personal marketplace:

```bash
mkdir -p ~/.codex/plugins ~/.agents/plugins
cp -R /path/to/instploy-chatgpt-plugin ~/.codex/plugins/instploy
ln -sfn ~/.codex/plugins/instploy ~/.agents/plugins/instploy
```

Create `~/.agents/plugins/marketplace.json`:

```json
{
  "name": "local-instploy",
  "interface": {
    "displayName": "Local InstPloy"
  },
  "plugins": [
    {
      "name": "instploy",
      "source": {
        "source": "local",
        "path": "./instploy"
      },
      "policy": {
        "installation": "AVAILABLE",
        "authentication": "ON_INSTALL"
      },
      "category": "Developer Tools"
    }
  ]
}
```

4. Restart ChatGPT desktop (or refresh Plugins), install **InstPloy**, open a **new chat**

## Security

- Never commit real Bearer tokens
- Plugin files only contain placeholders / instructions
