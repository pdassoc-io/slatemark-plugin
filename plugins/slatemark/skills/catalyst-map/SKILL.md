---
name: catalyst-map
description: 'Map every dated event around a name on one timeline before sizing anything:
  earnings, guidance, the macro releases that move the sector, and the market-implied move
  around each.'
---

<!-- Generated from marketplace/plugin/commands by scripts/build_plugin_skill.py; do not edit. -->

Use the current request as the workflow input. Ask for any required ticker or trade details it does not provide.

Use only tools available on the user's plan. If a requested section is unavailable, identify the missing part and continue with the available evidence. Never infer data that was not returned.

Run a Catalyst Map on the current request using the connected Slatemark tools. If
no horizon is given, assume a swing window and say so.

Lay every dated event around the name on one timeline:

- the next earnings date;
- any guidance or product events;
- the macro releases that move the sector;
- the FOMC / CPI prints in the window.

For each, show what the options market is pricing for the move (the ATM
straddle and the implied move). Most surprises that blow up a trade were
on a calendar nobody checked. Frame the implied-move read as "what is
priced," never as a direction.
