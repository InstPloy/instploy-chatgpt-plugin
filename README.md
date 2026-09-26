# InstPloy ChatGPT Plugin

ChatGPT / Codex marketplace that ships the InstPloy Agent Plugin.

> Cursor users: use https://github.com/InstPloy/instploy-cursor-plugin

## Repo layout

```text
.
├── .agents/plugins/marketplace.json   # required marketplace manifest
└── plugins/instploy/                  # the InstPloy plugin
    ├── plugin.json
    ├── .codex-plugin/plugin.json
    └── skills/instploy-mcp/SKILL.md
```

## Install marketplace from GitHub

```bash
codex plugin marketplace add InstPloy/instploy-chatgpt-plugin
```

Or with SSH:

```bash
codex plugin marketplace add git@github.com:InstPloy/instploy-chatgpt-plugin.git
```

Then open ChatGPT / Codex Plugins, pick the **InstPloy** marketplace, and install **instploy**.

## Connect InstPloy MCP

1. Enable **Developer mode**: Settings → Security and login → Developer mode
2. Plugins → **+** → register your MCP URL + Bearer token:

```json
"instploy": {
  "url": "https://YOUR_INSTANCE.instploy.com/instploy/manager/mcp",
  "headers": {
    "Authorization": "Bearer YOUR_TOKEN_HERE"
  }
}
```

3. Start a **new chat** after installing the plugin

## Security

- Never commit real Bearer tokens
- Plugin files only contain placeholders / instructions
