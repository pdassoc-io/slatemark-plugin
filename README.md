# Slatemark plugin marketplace

**No signals. Receipts.**

This public repository distributes Slatemark's optional client plugins for
Claude and Codex. Both packages connect to the same OAuth-protected Slatemark
MCP server and install user-chosen methodology alongside it. The AI client
creates each response. Slatemark does not host a model or generate the reply.

Git marketplace availability is not a Claude or OpenAI directory listing.
Claude's connector-only listing is accepted separately; the native Codex
package has not been submitted to or accepted by OpenAI for the universal
Plugins Directory.

## Install for Claude

For the shortest connector-only setup, open the accepted
[Slatemark connector listing](https://claude.ai/directory/connectors/slatemark),
choose **Connect**, and approve the sign-in. The connector does not require
this plugin or the skill.

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

Neither git install registers a ChatGPT app. ChatGPT availability requires a
separate OpenAI Developer Platform submission and approval.

## Connection and plans

The packages connect to `https://slatemark.ai/mcp` with OAuth. There is no
token to paste. A Slatemark account is required. Free includes one constrained
AI-client connection. Plus adds current brokerage Account Data, available
past fills imported into the trade journal, available new fills imported
periodically, short interest history from FINRA, additional active AI-client
connections, and a higher fair-use limit. Sign up at <https://slatemark.ai>.

After installation, start with one focused workflow instead of a blank chat:
<https://slatemark.ai/first-workflow>.

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
