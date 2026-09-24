---
description: Review a proposed trade against relevant evidence, the user's framework, and recorded intent.
argument-hint: "[ticker] [horizon]"
---

Use only tools available on the user's plan. Read saved context before
asking for missing inputs. Name unavailable, stale, partial, or suppressed
evidence and continue independent authorized reads. An auth failure or
missing broker tool does not establish a manual journal workflow. Never
infer data that was not returned. Cite sources, dates, and coverage.
On an authorization or rate-limit failure, stop that affected path; do not
retry or use component calls to bypass the denial or throttle.

Run a Pre-Trade Brief on $ARGUMENTS using the connected Slatemark tools.
Use the user's stated or saved horizon. Otherwise use the installed
analyst's default (or an explicitly labeled exploratory swing view when
none is installed); confirm before recording it as the user's intent.

Select the evidence that could change this thesis: trend and key levels,
next catalyst, relevant options context, and the macro backdrop. Current
chains supply per-expiration IV/skew and straddle marks, not historical
IV rank or percentile. Name that gap unless a historical IV source exists.

Use `list_rules` / `get_rule` for the user's discipline. For book-dependent
claims, read authorized `get_snaptrade_book_snapshot` holdings, then
`get_position_context` for intent and `get_account_profile(account_id=...)`
for the exact account key; check `_matched_account_key`. Journal entries
alone are not the book. Ask only for missing inputs needed by the next
step; a missing size does not block independent thesis research.

Synthesize support, counterevidence, uncertainty, and what would falsify
the thesis. Use the user's stated invalidation or name it as unresolved;
never invent it or direct a transaction. Offer an opening-intent draft
only if it fits the request, and honor a declined journaling offer.
