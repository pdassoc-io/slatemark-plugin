---
description: Run a cross-asset regime check before any single-name view — the curve, the dollar, credit, financial conditions, and vol, plus where the dislocations are.
argument-hint: (no arguments)
---

Run a Regime Check using the connected Slatemark tools. Pull the
cross-asset backdrop into one read before taking any single-name view.

Start with `analyze_market_regime`, the one-call composite that fetches
the whole backdrop in a single pass:

- the rate complex and yield-curve slope (steepening / flattening,
  inverted / positive);
- the dollar trend;
- the high-yield vs investment-grade credit ratio and its percentile;
- the vol regime (VIX level and percentile, plus SPY realized-vol
  percentile);
- a rolling cross-asset correlation matrix over the major assets, with
  the stock-bond correlation called out.

It runs on bare Yahoo, so it works with no broker link. Reach for the
individual tools only to drill into a reading that stands out or to add
context the composite does not carry: real yields and a
financial-conditions read (FRED series), recent Treasury auction demand
and TGA cash, or a longer correlation history.

Then name the regime and ask where the dislocations are: the
cross-asset tension worth watching. Frame it as a read of the weather,
not a position. The question is what backdrop the user is trading in,
never a call to act.
