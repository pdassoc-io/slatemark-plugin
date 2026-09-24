# Slatemark Claude plugin

**Market data and analytics for your AI.**

This bundle connects supported Claude clients to Slatemark's delayed market
data, technical calculations, SEC filings, and macroeconomic research. Your
private journal and the bundled senior-analyst skill are optional context;
Claude Code also receives workflow slash commands. Slatemark supplies factual
tool results, and Claude creates the response.

The Claude provider plugin is submitted and pending review. It has no public
plugin listing URL, so use the Git marketplace install path below for the
full bundle. For connector-only setup,
open the accepted
[Slatemark connector listing](https://claude.ai/directory/slatemark),
choose **Add** or **Connect**, and approve the sign-in. The connector does
not require this plugin or the skill. The exact connector URL is not the plugin
listing; the standalone customized skill has no separate listing recorded.

The plugin installs on claude.ai, in Claude Desktop, and in
Claude Code.

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
account at install or on first tool use. There is no token to paste.
In Claude Code, run `/mcp` if you want to trigger or check the sign-in.

A Slatemark account is required. Free includes one constrained
AI-client connection. Plus adds current brokerage Account Data,
available booked-activity and backfill import, periodic reconciliation, FINRA,
additional active AI-client connections, and higher fair-use limits.

## Try this first

After install, use the Free research workflow at
<https://slatemark.ai/first-workflow>:

> Show AAPL's latest available quote and latest non-null daily RSI(14) and
> ATR(14). Keep quote and indicator timestamps separate, and include each
> tool's source plus available `as_of`, `fetched_at`, and `data_quality` fields.

It needs no journal entry, brokerage link, paid plan, or provider key. It does
require an authenticated, available Free connection, sufficient daily history,
and an available market-data source. If a value or source is unavailable,
Claude should say so without inventing evidence. The page also offers
additional research and optional journal workflows.

## What's in the box

- **Remote MCP connector** (`https://slatemark.ai/mcp`, OAuth): the same
  hosted server as every other supported client, with factual research tools
  available on your plan and your optional private journal.
- **`senior-analyst` skill**: bundled visible methodology Claude can
  use with the tools. Factual lookups do not need a session-status or journal
  read; broader reviews use saved context only when relevant.
- **Workflow slash commands** (Claude Code):
  - `/slatemark:catalyst-map [ticker] [horizon]`
  - `/slatemark:regime-check`
  - `/slatemark:pre-trade-brief [ticker] [horizon]`
  - `/slatemark:position-review [ticker]`
  - `/slatemark:earnings-setup [ticker]`
  - `/slatemark:post-mortem [ticker]`

## Notes

- Market, research, and brokerage access is read-only. User-directed journal
  writes change only your Slatemark records. Slatemark never places,
  modifies, or cancels an order; every trading decision is yours. Nothing
  here is personalized investment advice.
- Market data is approximately 15 minutes delayed and labeled with its
  freshness. Brokerage connections provide Account Data, not market data.
  Option-chain snapshots are delayed, available only where listed,
  contain no Greeks, and use indicative, non-executable marks.
- The bundled `skills/senior-analyst/SKILL.md` is **generated** from the
  canonical templated source in the private `pdassoc-io/slatemark` repo
  (`skills/senior-analyst/`) via `scripts/build_plugin_skill.py`
  (rendered with defaults). Don't edit it by hand; edit the source and
  re-run the script. A test (`tests/test_plugin_skill_in_sync.py`) fails
  if the two drift. This Claude package is composed with the native Codex
  package and published to the public `pdassoc-io/slatemark-plugin` repo by
  `scripts/publish_plugin_marketplace.sh`.

## Compatible AI clients

This package is specific to Claude. The same public git marketplace also
contains a native Codex package under `plugins/slatemark/`; the OpenAI
submission is pending review and is not an accepted directory listing. Other
supported clients can connect to the hosted server at
`https://slatemark.ai/mcp` using their own setup flow. Claude's connector
acceptance does not confer an OpenAI listing.
