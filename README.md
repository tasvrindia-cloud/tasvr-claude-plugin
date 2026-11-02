# TASVR for Claude

Make Indian photography from inside Claude. You describe the brief, and
Claude plans the shots, asks who should be in them, shows you the credit
cost, and renders them through the TASVR engine. Every person, place and
piece of wardrobe in the image comes from TASVR's catalog of real
communities and locations.

## What you need

- A TASVR Pro or Enterprise plan.
- An API key from tasvr.ai: **Settings → Developer & API Keys → Create
  key**. It starts with `tasvr_sk_live_` and is shown only once.

## Install (Claude Code)

```
/plugin marketplace add tasvrindia-cloud/tasvr-claude-plugin
/plugin install tasvr@tasvr
```

Claude Code asks for your API key when you enable the plugin and keeps it
in your system's secure store.

## What's inside

| Skill | Use it for |
| --- | --- |
| `shoot-a-set` | Turning a campaign brief into a shot list, then a set of images |
| `cast-a-person` | Choosing who appears, with the right community, region and look |
| `references-and-edits` | Using your product or pose photo, and changing finished images |

The plugin connects Claude to `https://www.tasvr.ai/api/mcp`. Each image
spends credits from your TASVR account. Claude shows the cost and waits for
your yes before it renders anything.

Help: support@tasvr.ai · https://www.tasvr.ai/mcp
