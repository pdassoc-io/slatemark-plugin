# Slatemark agent plugin

**Check your risk before you take the trade.**

This package connects a supported AI client to Slatemark: the remote MCP
server for delayed market data, technical calculations, SEC filings, and
macroeconomic research, plus bundled analyst and workflow skills. Your private
journal and framework rules are optional context. Slatemark supplies factual
tool results; your AI client creates the response.

The package follows the Agent Plugins 1.0 format
(<https://agent-plugins.org/specification>): `plugin.json` is the manifest,
`mcp.json` declares the Slatemark server, and `skills/` holds one directory per
skill. `mcp_config.json` declares the same server for AI clients that read
that file instead. The package has no commands, hooks, agents, or executable
code. Install it with
your AI client's plugin install flow, pointed at this `slatemark` directory.
Slatemark generates the `skills/` files when it publishes the package, so a
copy taken from Slatemark's source repository needs
`python scripts/build_plugin_skill.py agent` before it is installed.

## Start here

Use the first Free research workflow at
<https://slatemark.ai/first-workflow>:

> Show AAPL's latest available quote and latest non-null daily RSI(14) and
> ATR(14). Keep quote and indicator timestamps separate, and include each
> tool's source plus available `as_of`, `fetched_at`, and `data_quality` fields.

It needs no journal entry, brokerage link, paid plan, or provider key. It does
require an authenticated, available Free connection, sufficient daily history,
and an available market-data source. Missing values or source failures remain
missing. For other research or recorded-trade tasks, ask for a focused skill
by name:

- `catalyst-map` for dated events around a name.
- `regime-check` for the cross-asset backdrop. **Plus.**
- `pre-trade-brief` for a ticker and horizon.
- `position-review` for a position you already hold. **Plus.**
- `earnings-setup` for the next earnings event. **Plus.**
- `post-mortem` for a trade you closed.

Each workflow uses only the data available on the user's plan, names any
unavailable section, and continues with the evidence it can retrieve. The
broader `analytical-framework` skill provides optional methodology alongside
these focused workflows. Its generated frontmatter carries the published skill
version and content hash.

## Connection and plans

The package connects to `https://slatemark.ai/mcp` over Streamable HTTP.
Sign-in uses OAuth, which the Agent Plugins format leaves to your AI client.
There are no static credentials in the package and no token to paste. A
Slatemark account is required. Free includes one constrained MCP connection.
Plus adds current brokerage Account Data, available past booked activity
imported into the trade journal, newly available booked activity imported
periodically, short interest history from FINRA, additional active AI-client
connections, and a higher fair-use limit.

## Boundaries

Brokerage, order, trading, and funds access is read-only. Slatemark never
places, modifies, or cancels an order; every trading decision is yours.
User-directed journal writes change only your Slatemark records; the Plus
booked-activity imports described above add brokerage activity to your trade
journal. Nothing here is personalized investment advice, and Slatemark is not
a registered investment adviser, broker-dealer, or fiduciary.

Market data is approximately 15 minutes delayed and labeled with its
freshness. Brokerage connections provide Account Data, not market data.
Option-chain snapshots are delayed, available only where listed, contain no
Greeks, and use indicative, non-executable marks.

## Distribution status

Slatemark distributes this package only through the public
`pdassoc-io/slatemark-plugin` Git repository. Git availability is not a
listing in any AI client's plugin directory or marketplace. The #202
combined-service gate is complete; the package must continue to preserve the
reviewed read-only, no-embedded-inference product shape.

## Privacy and support

Slatemark's [Privacy Policy](https://slatemark.ai/privacy) and
[Terms of Service](https://slatemark.ai/terms) cover the hosted service this
package connects to. For support, email <support@slatemark.ai>.

## License / use

© 2026 PD&A LLC. This package is published solely for use with the
hosted Slatemark service. It is not open-source software. You may download,
install, and privately modify this package to connect to your Slatemark
account, but you may not redistribute it. See the LICENSE file for full usage
rights and disclaimers.
