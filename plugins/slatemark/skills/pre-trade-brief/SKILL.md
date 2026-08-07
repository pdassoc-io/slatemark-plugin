---
name: pre-trade-brief
description: 'Run a pre-trade brief on a ticker before committing risk: trend and levels,
  the next catalyst, options skew and IV, the macro backdrop, and where the thesis breaks.'
---

<!-- Generated from marketplace/plugin/commands by scripts/build_plugin_skill.py; do not edit. -->

Use the current request as the workflow input. Ask for any required ticker or trade details it does not provide.

Use only tools available on the user's plan. If a requested section is unavailable, identify the missing part and continue with the available evidence. Never infer data that was not returned.

Run a Pre-Trade Brief on the current request using the connected Slatemark tools.
If no horizon is given, assume a swing (multi-day to multi-week) view and
say so explicitly.

Decompose across tools and hand back one brief, not a blurb:

- the multi-week trend with key support and resistance, ATR, and recent
  volume profile;
- the next catalyst on the calendar and how the name has reacted to that
  event historically;
- today's options skew and the 30-day IV percentile;
- the macro backdrop framing the window.

Always close with the invalidation level: where does the thesis break,
and what would confirm versus reject a hold of the key level? This is an
open analysis the user takes into their own decision, never a
recommendation to buy or sell.
