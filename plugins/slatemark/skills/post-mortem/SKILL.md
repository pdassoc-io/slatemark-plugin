---
name: post-mortem
description: Review a completed trade against recorded intent and preserve the user's own
  explanation.
---

<!-- Generated from marketplace/plugin/commands by scripts/build_plugin_skill.py; do not edit. -->

Use the current request as the workflow input. Ask for any required ticker or trade details it does not provide.

Use only tools available on the user's plan. Read saved context before
asking for missing inputs. Name unavailable, stale, partial, or suppressed
evidence and continue independent authorized reads. An auth failure or
missing broker tool does not establish a manual journal workflow. Never
infer data that was not returned. Cite sources, dates, and coverage.
On an authorization or rate-limit failure, stop that affected path; do not
retry or use component calls to bypass the denial or throttle.

Run a Post-Mortem on the trade described in the current request using the
connected Slatemark tools. Read the existing record before asking for
facts or creating another record. With an authorized linked broker and
a same-day execution, check executed orders before booked transactions.
An order may appear first, but booked activity remains canonical for
financial outcomes. Until it arrives, capture the user's rationale; do not
hand-close the entry or invent P&L or a manual financial child. If order
and booked activity describe the same execution, never count both.
Sync now cannot force upstream publication; no new activity does not
disprove the execution. Do not infer any state the tools did not return.

- Compare recorded intent and what happened, keeping observations separate
  from causal interpretation. Missing records cannot prove bad discipline.
- Preserve the user's own rationale and applicable canonical tags. For a
  booked partial reduction, use `annotate_journal_activity` with the reason
  verbatim; leave financial facts and parent status unchanged. It is not
  a Scorecard outcome. Re-read before retrying an uncertain annotation.
- In a verified manual workflow (manual record and established absence of
  a current brokerage link), a full executed close updates the existing
  parent with `status="closed"`, user-supplied `exit_fill_price`, `closed_at`,
  and net `user_realized_pnl` after fees. Without that P&L it is logged,
  not scored. A manual partial execution instead uses statusless
  `record_journal_activity`, preserving the parent's original quantity.
  Missing tools, failed reads, and auth errors do not prove this eligibility.
- Save only authorized user content. Ask for missing facts, not repeated
  permission to record facts already supplied for that purpose. Do not
  backdate an exit plan or manufacture a lesson from a single outcome.

Identify a tentative process observation only when evidence supports it.
The user's own reasoning stays theirs; never direct the next trade.
