# Slatemark Claude plugin marketplace

**No signals. Receipts.**

This repository is an optional Claude plugin marketplace. The plugin
bundles Slatemark's remote MCP connector (read-only delayed market
data, macro, filings, and your own trade journal), the
senior-analyst skill, and workflow slash commands for
[Claude Code](https://code.claude.com). Claude creates the response
using those tools and the installed skill. Slatemark does not host a
model or generate the reply.

For the shortest connector-only setup, open the accepted
[Slatemark connector listing](https://claude.ai/directory/connectors/slatemark),
choose **Connect**, and approve the sign-in. The connector does not
require this plugin or the skill. Neither this plugin nor the
standalone skill is claimed as a Claude directory listing.

## Install

**Claude Code:**

```text
/plugin marketplace add pdassoc-io/slatemark-plugin
/plugin install slatemark@slatemark-plugin
```

**Claude Desktop / claude.ai:** open **Customize → Plugins**, choose
**Add from a repository**, paste
`https://github.com/pdassoc-io/slatemark-plugin`, then install
**Slatemark**.

Claude opens an OAuth sign-in in your browser to connect your Slatemark
account at install or on first tool use. There is no token to paste.
In Claude Code, run `/mcp` if you want to trigger or check the sign-in.

A Slatemark account is required. Free includes one constrained
AI-client connection. Plus adds current brokerage Account Data,
available fill and backfill import, periodic reconciliation, FINRA,
additional active AI-client connections, and higher fair-use limits.
Sign up at <https://slatemark.ai>.

## Try this first

After install, start with one workflow instead of a blank chat:
<https://slatemark.ai/first-workflow>. The page gives copyable prompts
for a pre-trade brief, position review, earnings setup, regime check,
catalyst map, post-mortem, and journal entry.

## What's in the box

- **Remote MCP connector**: `https://slatemark.ai/mcp`, OAuth. The
  read-only tool surface available on your plan plus your per-user
  trade journal.
- **`senior-analyst` skill**: a user-installed methodology Claude can
  use with the tools.
- **Slash commands** (Claude Code): `/slatemark:pre-trade-brief`,
  `/slatemark:post-mortem`, `/slatemark:regime-check`,
  `/slatemark:position-review`, `/slatemark:catalyst-map`,
  `/slatemark:earnings-setup`.

See [`plugin/README.md`](plugin/README.md) for the plugin's own readme.

## Compatible AI clients

This marketplace is specific to Claude. Any compatible AI client can
connect to the same hosted server at `https://slatemark.ai/mcp` using
its own setup flow. ChatGPT will use a separate connector-only app
after its OpenAI Apps SDK submission; Claude's listing does not publish
that app.

## What this is and isn't

Slatemark is read-only research and journaling. It never places,
modifies, or cancels an order; every trading decision is yours. Nothing
here is personalized investment advice, and Slatemark is not a
registered investment adviser, broker-dealer, or fiduciary.

Market data is approximately 15 minutes delayed and labeled with its
freshness. Brokerage connections provide Account Data, not market data.
Option-chain snapshots are delayed, available only where listed, contain
no Greeks, and use indicative, non-executable marks.

## License / use

© Slatemark. This plugin is published for use with the hosted Slatemark
service (the connector requires a Slatemark account). The bundled
methodology skill and commands are provided for that use and are not
released under an open-source redistribution license. The Slatemark
server code is not distributed here.

> Maintainers: this repository is **generated** from the private
> `pdassoc-io/slatemark` source (`marketplace/`). Do not hand-edit it;
> edit the source and run `scripts/publish_plugin_marketplace.sh`.
