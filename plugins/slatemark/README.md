# Slatemark OpenAI plugin

**No signals. Receipts.**

This optional plugin wires Codex to Slatemark: the remote MCP server for
read-only delayed market data, macro data, filings, framework rules, and your
trade journal, plus user-installed analyst and workflow skills. The AI client
creates the response using those tools and skills. Slatemark does not host a
model or generate the reply.

## Start here

Try one focused workflow instead of a blank task:

- `$pre-trade-brief` for a ticker and horizon.
- `$position-review` for a position you already hold. **Plus.**
- `$earnings-setup` for the next earnings event. **Plus.**
- `$regime-check` for the cross-asset backdrop. **Plus.**
- `$catalyst-map` for dated events around a name.
- `$post-mortem` for a trade you closed.

Each workflow uses only the data available on the user's plan, names any
unavailable section, and continues with the evidence it can retrieve. The
broader `$senior-analyst` skill provides a methodology alongside these focused
workflows. Its generated frontmatter carries the published skill version,
content hash, and freshness-check URL.

## Connection and plans

The plugin connects to `https://slatemark.ai/mcp` with OAuth. There are no
static credentials in the package. A Slatemark account is required. Free
includes one constrained MCP connection. Plus adds current brokerage Account
Data, available past fills imported into the trade journal, available new fills
imported periodically, short interest history from FINRA, additional active
AI-client connections, and a higher fair-use limit.

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
`pdassoc-io/slatemark-plugin` git marketplace for Codex. It has no registered
ChatGPT technical app ID or `.app.json` mapping, and it has not been submitted
to or accepted for OpenAI's universal Plugins Directory. The #202
combined-service gate is complete; the package must continue to preserve the
reviewed read-only, no-embedded-inference product shape.

© Slatemark. The bundled methodology and workflow skills are provided for use
with the hosted Slatemark service and are not released under an open-source
redistribution license. The Slatemark server code is not distributed here.
