# Slatemark Claude plugin

**No signals. Receipts.**

This optional bundle wires Claude to Slatemark: the remote MCP connector
(read-only delayed market data, macro, filings, and your trade journal)
plus a user-installed senior-analyst skill, and in Claude Code, workflow
slash commands. Claude creates the response using those tools and the
installed skill. Slatemark does not host a model or generate the reply.

For the shortest connector-only setup, open the accepted
[Slatemark connector listing](https://claude.ai/directory/connectors/slatemark),
choose **Connect**, and approve the sign-in. The connector does not
require this plugin or the skill. Neither this plugin nor the
standalone skill is claimed as a Claude directory listing.

The optional plugin installs on claude.ai, in Claude Desktop, and in
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
available fill and backfill import, periodic reconciliation, FINRA,
additional active AI-client connections, and higher fair-use limits.

## Try this first

After install, start with one workflow instead of a blank chat:
<https://slatemark.ai/first-workflow>. The page gives copyable prompts
for a pre-trade brief, position review, earnings setup, regime check,
catalyst map, post-mortem, and journal entry.

## What's in the box

- **Remote MCP connector** (`https://slatemark.ai/mcp`, OAuth): the same
  hosted server as every other client, with the read-only tool surface
  available on your plan and your per-user trade journal.
- **`senior-analyst` skill**: a user-installed methodology Claude can
  use with the tools. At session start it calls `get_session_status` to
  choose connected-account or manual journal context.
- **Workflow slash commands** (Claude Code):
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
contains a native Codex package under `plugins/slatemark/`; it has no ChatGPT
app mapping and is not an accepted OpenAI directory listing. Any compatible
AI client can connect to the hosted server at `https://slatemark.ai/mcp`
using its own setup flow. Claude's connector acceptance does not confer an
OpenAI listing.
