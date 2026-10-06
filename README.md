# Ad Army for Claude

Connect Claude to your [Ad Army](https://ad.army) workspace. Claude can find and
inspect your Playground boards, catalogue creative references, and plan,
estimate and produce product images, video ads, captioned recuts and narrated
explainers, spending only within a credit budget you approve.

The plugin works in Claude Code, claude.ai, the Claude desktop app and Cowork.

## What's inside

- **Ad Army connector**: the hosted Ad Army MCP server at
  `https://app.ad.army/api/mcp`. You sign in to Ad Army and choose which
  workspace and permissions Claude may use.
- **Skills** that teach Claude how to use Ad Army well:
  - `ad-army`: resolving boards and assets, approving and tracking credit
    budgets, following and resuming jobs, uploading media, and saving results to
    a Playground.
  - `product-ad`: product image variations, one product in several worlds, and
    cinematic character-led product video ads.
  - `recut`: shorter captioned cuts of existing footage.
  - `explainer`: narrated explainer videos from a grounded script.

The skills load the current step-by-step recipes from Ad Army itself
(`list_recipes` and `get_recipe`), so they stay in step with the product.

## Install

### Claude Code

```text
/plugin marketplace add ad-army/claude-plugin
/plugin install ad-army@ad-army
```

Then run `/mcp`, select the Ad Army server and sign in.

### claude.ai, Claude desktop and Cowork

1. Open **Customize > Plugins**, add a marketplace, and enter
   `ad-army/claude-plugin`.
2. Install **Ad Army**.
3. On the plugin's **Connectors** tab, connect Ad Army and sign in.

On a Team or Enterprise plan, an Owner can add this repository under
**Organization settings > Plugins & skills** to make the plugin available to
everyone in the organization. Each member still connects with their own Ad Army
account.

## Permissions and credits

Connecting is free and adds no credits. On the consent page you pick the
workspace and the permissions Claude may use: reading the workspace, editing
Playgrounds, analysing media, generating media, assembling videos and, if you
choose, importing outside media. You can revoke a connection at any time from
**Workspace Settings > Connected assistants** in Ad Army.

Generation, analysis, transcription and rendering use the connected workspace's
existing credits. Claude estimates the work first, asks you to approve a total
budget, and every paid step is checked against that budget and against your
per-operation limit. Reading, estimating, previews and board edits are free.

Review generated media before you publish it.

## What this plugin runs and sends

The plugin contains no executable code, hooks or local servers: it is a
connector entry and Markdown instructions. Claude talks only to the Ad Army MCP
server named above, over HTTPS, authenticated with OAuth. Tool calls send the
prompts, asset references and settings needed for the work you ask for to your
Ad Army workspace. Media you upload goes directly to Ad Army storage.

- Privacy policy: https://ad.army/privacy
- Terms of service: https://ad.army/terms
- Support: https://ad.army/support or support@ad.army

## License

[MIT](LICENSE)
