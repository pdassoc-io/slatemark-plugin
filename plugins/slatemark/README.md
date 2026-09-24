# Slatemark OpenAI plugin

**Market data and analytics for your AI.**

This plugin wires Codex to Slatemark: the remote MCP server for
delayed market data, technical calculations, SEC filings, and macroeconomic
research, plus bundled analyst and workflow skills. Your private journal and
framework rules are optional context. Slatemark supplies factual tool results;
Codex creates the response.

## Start here

Use the first Free research workflow at
<https://slatemark.ai/first-workflow>:

> Show AAPL's latest available quote and latest non-null daily RSI(14) and
> ATR(14). Keep quote and indicator timestamps separate, and include each
> tool's source plus available `as_of`, `fetched_at`, and `data_quality` fields.

It needs no journal entry, brokerage link, paid plan, or provider key. It does
require an authenticated, available Free connection, sufficient daily history,
and an available market-data source. Missing values or source failures remain
missing. For other research or recorded-trade tasks, use a focused skill:

- `$catalyst-map` for dated events around a name.
- `$regime-check` for the cross-asset backdrop. **Plus.**
- `$pre-trade-brief` for a ticker and horizon.
- `$position-review` for a position you already hold. **Plus.**
- `$earnings-setup` for the next earnings event. **Plus.**
- `$post-mortem` for a trade you closed.

Each workflow uses only the data available on the user's plan, names any
unavailable section, and continues with the evidence it can retrieve. The
broader `$senior-analyst` skill provides optional methodology alongside these
focused workflows. Its generated frontmatter carries the published skill
version, content hash, and freshness-check URL.

## Connection and plans

The plugin connects to `https://slatemark.ai/mcp` with OAuth. There are no
static credentials in the package. A Slatemark account is required. Free
includes one constrained MCP connection. Plus adds current brokerage Account
Data, available past booked activity imported into the trade journal, newly
available booked activity imported periodically, short interest history from
FINRA, additional active AI-client connections, and a higher fair-use limit.

## Boundaries

Brokerage, order, trading, and funds access is read-only. Slatemark never
places, modifies, or cancels an order; every trading decision is yours. The
journal can write only user-authored records to your Slatemark store. Nothing
here is personalized investment advice, and Slatemark is not a registered
investment adviser, broker-dealer, or fiduciary.

Market data is approximately 15 minutes delayed and labeled with its
freshness. Brokerage connections provide Account Data, not market data.
Option-chain snapshots are delayed, available only where listed, contain no
Greeks, and use indicative, non-executable marks.

## Distribution status

This package is distributed through the public
`pdassoc-io/slatemark-plugin` git marketplace for Codex. The OpenAI submission
is pending review, and the package is not yet accepted or published in
OpenAI's universal Plugins Directory. Git availability is not an OpenAI
directory listing. It has no registered ChatGPT technical
app ID or `.app.json` mapping in this tree. The #202
combined-service gate is complete; the package must continue to preserve the
reviewed read-only, no-embedded-inference product shape.

© Slatemark. The bundled methodology and workflow skills are provided for use
with the hosted Slatemark service and are not released under an open-source
redistribution license. The Slatemark server code is not distributed here.
