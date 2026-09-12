---
description: Review current evidence against a held position's recorded thesis and framework rules.
argument-hint: [ticker]
---

Use only tools available on the user's plan. Read saved context before
asking for missing inputs. Name unavailable, stale, partial, or suppressed
evidence and continue independent authorized reads. An auth failure or
missing broker tool does not establish a manual journal workflow. Never
infer data that was not returned. Cite sources, dates, and coverage.
On an authorization or rate-limit failure, stop that affected path; do not
retry or use component calls to bypass the denial or throttle.

Run a Position Review on $ARGUMENTS using the connected Slatemark tools.
Start with `get_position_context(symbol)` for journal intent and holding
evidence, including manual entries when no broker is available. Read a
specific `get_journal_entry` if its thesis preview is truncated. Empty
journal entries do not mean no holding; preserve `broker_position.status`
and `journal_coverage`, including unknown or unauthorized states.

Compare the original thesis and the user's current `active_plan` with
current price, relevant levels, catalysts, and applicable framework rules
(`list_rules` / `get_rule`). For concentration, use an authorized
`get_snaptrade_book_snapshot`, not a journal-only inventory. For account
framing, use the exact key with `get_account_profile` and check
`_matched_account_key`; `_has_file` alone does not prove a match.

State supported changes, counterevidence, and unresolved questions. Ask
for original framing only if it is missing from the record. Do not direct
an add or trim, rewrite the user's plan, or journal an unsolicited review.
