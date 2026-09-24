# Slatemark plugin marketplace

**Market data and analytics for your AI.**

This public repository distributes Slatemark packages for supported Claude and
Codex clients. Both connect to the same OAuth-protected Slatemark MCP server
for delayed market data, technical calculations, SEC filings, and
macroeconomic research. Your private journal and the bundled methodology are
optional context. Slatemark supplies factual tool results; your AI client
creates each response.

Git marketplace availability is not a Claude or OpenAI directory listing. The
Claude provider plugin is submitted and pending review, with no public plugin
listing URL; Claude's published connector-only listing remains separate. The OpenAI submission
is pending review and is not yet accepted or published in the universal
Plugins Directory.

## Install for Claude

Use the public Git marketplace for the full bundle while the Claude provider
plugin is pending review. Do not invent a provider-plugin deep link. For connector-only setup,
open the accepted
[Slatemark connector listing](https://claude.ai/directory/slatemark),
choose **Add** or **Connect**, and approve the sign-in. The connector does
not require this plugin or the skill.

**Claude Code:**

```text
/plugin marketplace add pdassoc-io/slatemark-plugin
/plugin install slatemark@slatemark-plugin
```

**Claude Desktop / claude.ai:** open **Customize → Plugins**, choose
**Add from a repository**, paste
`https://github.com/pdassoc-io/slatemark-plugin`, then install **Slatemark**.

The Claude package includes the connector, the `senior-analyst` skill, and six
`/slatemark:*` workflow commands for Claude Code. See
[`plugin/README.md`](plugin/README.md).

## Install for Codex

```text
codex plugin marketplace add pdassoc-io/slatemark-plugin
codex plugin add slatemark@slatemark-codex-plugin
```

Start a new Codex task after installation and authenticate when prompted. The
native package includes the connector, the `senior-analyst` skill, and six
focused workflow skills. See
[`plugins/slatemark/README.md`](plugins/slatemark/README.md).

Neither git install registers a ChatGPT app. The OpenAI Developer Platform
submission is pending review; ChatGPT availability still requires approval and
publication.

## Connection and plans

The packages connect to `https://slatemark.ai/mcp` with OAuth. There is no
token to paste. A Slatemark account is required. Free includes one constrained
AI-client connection. Plus adds current brokerage Account Data, available
past booked activity imported into the trade journal, newly available booked
activity imported periodically, short interest history from FINRA, additional
active AI-client connections, and a higher fair-use limit. Sign up at
<https://slatemark.ai>.

After installation, start with this Free research workflow in a supported
client. Copy the full question from <https://slatemark.ai/first-workflow>:

> Show AAPL's latest available quote and latest non-null daily RSI(14) and
> ATR(14). Keep quote and indicator timestamps separate, and include each
> tool's source plus available `as_of`, `fetched_at`, and `data_quality` fields.

It needs no journal entry, brokerage link, paid plan, or provider key. It does
require an authenticated, available Free connection, sufficient daily history,
and an available market-data source. Report missing values or source failures
as missing; do not invent a result.

## What this is and isn't

Brokerage, order, trading, and funds access is read-only. Slatemark never
places, modifies, or cancels an order; every trading decision is yours. The
journal can write only user-authored records to your private Slatemark store.
Nothing here is personalized investment advice, and Slatemark is not a
registered investment adviser, broker-dealer, or fiduciary.

Market data is approximately 15 minutes delayed and labeled with its
freshness. Brokerage connections provide Account Data, not market data.
Option-chain snapshots are delayed, available only where listed, contain no
Greeks, and use indicative, non-executable marks.

## License / use

© Slatemark. These plugins are published for use with the hosted Slatemark
service. The bundled methodology and workflow content is not released under
an open-source redistribution license. The Slatemark server code is not
distributed here.

> Maintainers: this repository is **generated** from the private
> `pdassoc-io/slatemark` sources under `marketplace/` and
> `codex-marketplace/`. Do not hand-edit it; edit the sources and run
> `scripts/publish_plugin_marketplace.sh`.
