# TASVR for Claude

Make Indian photography from inside Claude. You describe the brief, and
Claude plans the shots, asks who should be in them, shows you the credit
cost, and renders them through the TASVR engine. Every person, place and
piece of wardrobe in the image comes from TASVR's catalog of real
communities and locations.

## What you need

- A TASVR Pro or Enterprise plan.

## Install (Claude Code)

```
/plugin marketplace add tasvrindia-cloud/tasvr-claude-plugin
/plugin install tasvr@tasvr
```

The first time Claude uses TASVR it opens TASVR's sign-in. Sign in with your
TASVR account and approve Claude on the consent page. You can disconnect it
any time in Settings → Developer & API Keys on tasvr.ai.

In claude.ai you can also connect without the plugin: Settings → Connectors →
Add custom connector → `https://www.tasvr.ai/api/mcp`.

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
