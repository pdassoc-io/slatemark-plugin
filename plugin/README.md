# Slatemark — Claude plugin

One install wires Claude to Slatemark: the remote MCP connector
(read-only market data, macro, filings, and your trade journal) plus the
senior-analyst skill — and, in Claude Code, the named analyst "moves" as
slash commands.

The plugin installs on claude.ai, in Claude Desktop, and in Claude
Code; the connector and skill are also available as two separate adds
from `claude.ai/directory` if you prefer the pieces individually.

## Install

**Claude Code:**

```text
/plugin marketplace add pdassoc-io/slatemark-plugin
/plugin install slatemark@slatemark-plugin
```

The first command registers the marketplace; the second installs the
plugin.

**Claude Desktop / claude.ai:** open **Customize → Plugins**, choose
**Add from a repository**, paste
`https://github.com/pdassoc-io/slatemark-plugin`, then install
**Slatemark**.

Claude opens an OAuth sign-in in your browser to connect your Slatemark
account — at install or on first tool use. There is no token to paste.
In Claude Code, run `/mcp` if you want to trigger or check the sign-in.

## What's in the box

- **Remote MCP connector** (`https://slatemark.ai/mcp`, OAuth) — the same
  hosted server as every other client, with the full read-only tool
  surface and your per-user trade journal.
- **`senior-analyst` skill** — the senior-trading-analyst methodology;
  it branches its journaling behavior on whether your broker is linked
  (it calls `get_session_status` at session start).
- **Slash commands** for the named moves (Claude Code):
  - `/slatemark:pre-trade-brief [ticker] [horizon]`
  - `/slatemark:post-mortem [ticker]`
  - `/slatemark:regime-check`
  - `/slatemark:position-review [ticker]`
  - `/slatemark:catalyst-map [ticker] [horizon]`
  - `/slatemark:earnings-setup [ticker]`

## Notes

- Read-only. Slatemark never places, modifies, or cancels an order; every
  trading decision is yours. Nothing here is personalized investment
  advice.
- The bundled `skills/senior-analyst/SKILL.md` is **generated** from the
  canonical templated source in the private `pdassoc-io/slatemark` repo
  (`skills/senior-analyst/`) via `scripts/build_plugin_skill.py`
  (rendered with defaults). Don't edit it by hand — edit the source and
  re-run the script. A test (`tests/test_plugin_skill_in_sync.py`) fails
  if the two drift. This whole `marketplace/` tree is published to the
  public `pdassoc-io/slatemark-plugin` repo by
  `scripts/publish_plugin_marketplace.sh`.
