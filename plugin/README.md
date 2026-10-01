# Slatemark Claude plugin

**Market data and analytics for your AI.**

This bundle connects supported Claude clients to Slatemark's delayed market
data, technical calculations, SEC filings, and macroeconomic research. Your
private journal and the bundled senior-analyst skill are optional context;
Claude Code also receives workflow slash commands. Slatemark supplies factual
tool results, and Claude creates the response.

For connector-only setup, open the
[Slatemark connector listing](https://claude.ai/directory/slatemark),
choose **Add** or **Connect**, and approve the sign-in. That listing installs
the connector only, without this plugin's skill or slash commands, and the
connector does not require them.

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

## Update in Claude Code

For an existing Git marketplace install, refresh the marketplace and then the
plugin:

```text
claude plugin marketplace update slatemark-plugin
claude plugin update slatemark@slatemark-plugin
claude plugin list
```

Restart an already running Claude Code session to load the update.

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
- **Skill version check.** If you ask whether the bundled skill is up to
  date, the skill tells Claude to send a plain HTTP GET to a public
  Slatemark endpoint, `https://slatemark.ai/skills/freshness`, carrying only
  the skill name and its published content hash. The request needs no
  sign-in and does not use the MCP connection. The response contains only
  version facts. If Claude cannot make HTTP requests, it gives you the URL
  to open yourself.
- The bundled `skills/senior-analyst/SKILL.md` is generated for each
  release from Slatemark's maintained source, so its changes arrive with
  plugin updates.
- Slatemark's [Privacy Policy](https://slatemark.ai/privacy) and
  [Terms of Service](https://slatemark.ai/terms) cover the hosted service
  this plugin connects to.

## Compatible AI clients

This package is specific to Claude. The same public Git marketplace also
contains a native Codex package under `plugins/slatemark/`. Other supported
clients can connect to the hosted server at `https://slatemark.ai/mcp` using
their own setup flow.

## License / use

© 2026 PD & Associates. This package is published solely for use with the
hosted Slatemark service. It is not open-source software. You may download,
install, and privately modify this package to connect to your Slatemark
account, but you may not redistribute it. See the LICENSE file for full usage
rights and disclaimers.
