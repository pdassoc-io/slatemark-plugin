---
name: post-mortem
description: 'Run a post-mortem on a trade you just closed: separate what happened from why,
  preserve its journal rationale, and tag it for Scorecard reconciliation.'
---

<!-- Generated from marketplace/plugin/commands by scripts/build_plugin_skill.py; do not edit. -->

Use the current request as the workflow input. Ask for any required ticker or trade details it does not provide.

Use only tools available on the user's plan. If a requested section is unavailable, identify the missing part and continue with the available evidence. Never infer data that was not returned.

Run a Post-Mortem on the trade described in the current request using the
connected Slatemark tools. If a broker is linked and the execution was
today, check executed orders before booked transactions. An order can
appear first, but booked activity remains canonical for the journal and
realized P&L. Spend the turn on the why while that activity is not yet
available.

- Separate *what happened* (the price action, the catalyst, the levels
  that held or broke) from *why it happened* (entry timing, sizing, the
  thesis, on-plan versus discretionary).
- Then record it: snap the setup to a canonical tag (use the tag tools)
  and preserve the user's rationale. With a broker linked, do not
  hand-close the entry or invent P&L while only an executed order is
  visible. The Strategy Scorecard updates after matching booked activity
  arrives and reconciles. If both order and activity are visible, treat
  them as the same execution and never count both. A successful Sync now
  with no newly booked activity does not disprove the execution or mean
  the journal is broken. Use direct tool results only; do not infer any
  state the tools did not return. With no broker linked, ask for
  the net realized P&L after fees and record it on the close, since that
  is what makes the trade score.
- Name the one repeatable lesson. Run this on winners and losers; the
  losers are where the lesson is.

This records the user's own reasoning. It is not advice and never tells
the user what to trade next.
