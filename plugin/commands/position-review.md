---
description: Re-underwrite a position you already hold as if deciding to enter today — does the thesis still hold at the current level, and where does it sit against your framework rules?
argument-hint: [ticker]
---

Run a Position Review on $ARGUMENTS using the connected Slatemark tools.
If a broker is linked, pull the holding and its context from the account
(use get_position_context); otherwise ask the user for their original
thesis.

Re-underwrite the position as if deciding to enter it today, not as a
comfortable re-read of why it was bought:

- Does the original thesis still hold at the level it trades now, around
  its key support and resistance?
- Where does the position sit against the relevant framework rules —
  concentration, the position lifecycle, and any hedge or sizing
  discipline that applies (use list_rules / get_rule)?

Keep it open-ended: ask whether the thesis holds, not whether to add or
trim. The decision stays with the user.
