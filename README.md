# Slatemark — Claude Code plugin marketplace

This repository is a [Claude Code](https://code.claude.com) plugin
marketplace. Adding it gives Claude Code one-install access to Slatemark:
the remote MCP connector (read-only market data, macro, filings, and
your own trade journal), the senior-analyst skill, and the named
analyst "moves" as slash commands.

## Install

```text
/plugin marketplace add pdassoc-io/slatemark-plugin
/plugin install slatemark@slatemark-plugin
```

On first tool use Claude Code opens an OAuth sign-in in your browser to
connect your Slatemark account. There is no token to paste. Run `/mcp`
if you want to trigger or check the sign-in.

A Slatemark account is required (free or Pro). Sign up at
<https://slatemark.ai>.

## What's in the box

- **Remote MCP connector** — `https://slatemark.ai/mcp`, OAuth. The full
  read-only tool surface plus your per-user trade journal.
- **`senior-analyst` skill** — the senior-trading-analyst methodology.
- **Slash commands** — `/slatemark:pre-trade-brief`,
  `/slatemark:post-mortem`, `/slatemark:regime-check`,
  `/slatemark:position-review`, `/slatemark:catalyst-map`,
  `/slatemark:earnings-setup`.

See [`plugin/README.md`](plugin/README.md) for the plugin's own readme.

## What this is and isn't

Slatemark is read-only research and journaling. It never places,
modifies, or cancels an order; every trading decision is yours. Nothing
here is personalized investment advice, and Slatemark is not a
registered investment adviser, broker-dealer, or fiduciary.

## License / use

© Slatemark. This plugin is published for use with the hosted Slatemark
service (the connector requires a Slatemark account). The bundled
methodology skill and commands are provided for that use and are not
released under an open-source redistribution license. The Slatemark
server code is not distributed here.

> Maintainers: this repository is **generated** from the private
> `pdassoc-io/slatemark` source (`marketplace/`). Do not hand-edit it;
> edit the source and run `scripts/publish_plugin_marketplace.sh`.
