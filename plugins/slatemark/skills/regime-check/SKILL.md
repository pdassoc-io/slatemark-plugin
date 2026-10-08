---
name: regime-check
description: Review the cross-asset backdrop using Slatemark's composite read, the cross-asset
  panel, and relevant follow-ups.
---

<!-- Generated from marketplace/plugin/commands by scripts/build_plugin_skill.py; do not edit. -->

Use only tools available on the user's plan. Read saved context before
asking for missing inputs. Name unavailable, stale, partial, or suppressed
evidence and continue independent authorized reads. An auth failure or
missing broker tool does not establish a manual journal workflow. Never
infer data that was not returned. Cite sources, dates, and coverage.
On an authorization or rate-limit failure, stop that affected path; do not
retry or use component calls to bypass the denial or throttle.

Run a Regime Check using the connected Slatemark tools. It combines two
independent reads; say which facts come from which.

- `analyze_market_regime` is Slatemark's fixed composite: the rate
  complex, dollar trend, credit ratio, volatility, and cross-asset
  correlations.
- `analyze_market_data_cross_asset_panel` reads a panel of instruments,
  ratios, and the fed funds futures path: the user's saved panel, or
  Slatemark's default when none is saved or a saved panel cannot be read.
  Call it without `panels` so a saved panel applies; pass `panels` only
  for instruments the user names in this request.

Both use delayed public market data and need no broker link. If one read
fails or is not on the user's plan, name it and continue with the other.

Read the panel in this order:

1. **Coverage.** State `panel_source`. `default` is Slatemark's default
   set, not a panel the user chose; users choose their own under
   Cross-asset panel on their Slatemark Profile page. `saved_panel:
   "unavailable"` means a saved panel could not be read. Give each
   panel's `bar_date`, flag `latest_bar_may_be_partial`, and name every
   `unavailable` symbol and every panel carrying `error`. Leave a missing
   panel missing.
2. **State.** Describe each panel from its returned numbers only. A
   ratio panel compares two prices: a rising ratio means the numerator
   outperformed the denominator. It is not a price difference.
3. **Relationships.** Report `correlation_shifts` with both windows, the
   leading `largest_moves` by `scaled_move`, and where related panels
   agree or disagree, such as the yen and franc pairs. Correlations
   leave out `alignment.unshared_dates`.
4. **Fed funds path.** Report the `anchor` and each solved meeting's
   implied rate and change as returned. Where `gap` stops the path, name
   its meeting and `missing_contracts`; never extend the path past a gap
   or rebuild it from a continuous `/ZQ` chart. Do not restate the path as
   a forecast or as the probability of a decision. `effr` is a reference
   value; the path does not depend on it. A block carrying `error` has no
   path.
5. **The user's lens.** When the user has said what they watch a panel
   for, in this conversation or in saved context, attribute that reading
   to them. It is their view, not Slatemark's, and it does not change the
   returned numbers.

Read the composite's components, windows, and coverage the same way. Use
individual tools only for relevant gaps or a requested deeper comparison,
such as real yields or financial conditions. Distinguish the computed
facts from your inference, weigh conflicting components and panels, and
describe what evidence would change the assessment. Do not present the
read as Slatemark's conclusion, and do not treat it as a prerequisite for
every single-name factual question or as a signal to act.
