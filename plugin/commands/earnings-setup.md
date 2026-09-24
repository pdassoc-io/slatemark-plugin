---
description: Review an earnings event using sourced dates, current option premiums, and supported historical reactions.
argument-hint: "[ticker]"
---

Use only tools available on the user's plan. Read saved context before
asking for missing inputs. Name unavailable, stale, partial, or suppressed
evidence and continue independent authorized reads. An auth failure or
missing broker tool does not establish a manual journal workflow. Never
infer data that was not returned. Cite sources, dates, and coverage.
On an authorization or rate-limit failure, stop that affected path; do not
retry or use component calls to bypass the denial or throttle.

Run an Earnings Setup on $ARGUMENTS using the connected Slatemark tools.
Read the event date and whether its timing is estimated. For relevant
expirations, use `analyze_option_chain` for ATM straddle marks, IV term
structure, and skew; apply `get_rule("options-liquidity-gates")` to quoted
contracts. State the expiration and timestamp of each comparison.

The straddle premium/underlying is a move proxy for that expiration,
not a one-sigma range, success probability, or isolated earnings-day move.
The current chain does not provide historical IV rank, percentile, or
prior event-implied moves. Cite those only from a separate historical
options source. Dated underlying history can establish past price
reactions, but cannot reconstruct past option premiums.

Explain what the evidence supports, competing explanations, and missing
comparisons. Do not infer a premium-buying or selling advantage from IV
alone, predict the print, or instruct an order.
