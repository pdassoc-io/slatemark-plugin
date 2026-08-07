---
name: post-mortem
description: 'Run a post-mortem on a trade you just closed: separate what happened from why,
  then journal it and tag the setup so it lands on your scorecard.'
---

<!-- Generated from marketplace/plugin/commands by scripts/build_plugin_skill.py; do not edit. -->

Use the current request as the workflow input. Ask for any required ticker or trade details it does not provide.

Use only tools available on the user's plan. If a requested section is unavailable, identify the missing part and continue with the available evidence. Never infer data that was not returned.

Run a Post-Mortem on the trade described in the current request using the
connected Slatemark tools. If a broker is linked, pull the
authoritative fill from the broker first rather than asking for the
numbers; the close reconciles itself, so spend the turn on the why.

- Separate *what happened* (the price action, the catalyst, the levels
  that held or broke) from *why it happened* (entry timing, sizing, the
  thesis, on-plan versus discretionary).
- Then record it: journal the trade and snap the setup to a canonical
  tag (use the tag tools) so it lands on the user's Strategy Scorecard.
  With a broker linked, say "logged," not "scored," until the poller
  reconciles the fill; a broker value always wins. With no broker
  linked, ask for the net realized P&L after fees and record it on the
  close, since that is what makes the trade score.
- Name the one repeatable lesson. Run this on winners and losers; the
  losers are where the lesson is.

This records the user's own reasoning. It is not advice and never tells
the user what to trade next.
