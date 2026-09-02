# Verification checklist — author completes before release

## Reproduce
- [x] Fresh fetch; row counts match PROVENANCE
- [x] Full pipeline re-run; outputs diff clean
- [x] Every README number re-derived from stats.json

## Source-level
- [x] Five episodes checked by hand against the source listing pages
- [x] Source vintages confirmed current
- [x] Licence terms of all three sources re-read; redistribution permitted

## Row-level spot checks (15 minimum)
- [x] Five products known from practice
- [x] Five extremes (longest, shortest, highest recurrence)
- [x] Five random (seed 7749 recorded)

## Judgment calls owned
- [x] **V1** 30-day episode gap. Ruled and parameterised; sensitivity reported.
- [x] **V2** Open episodes censored, not truncated.
- [x] **V3** Product identity drift not corrected in v0.1.0; documented as limitation 4.
- [x] **V4** Ingredient roll-up uses the directory's ingredient key.
- [x] **V5** Primary class used where several apply.

## Before public
- [x] Prose rewritten in my own voice
- [x] Figures regenerated with --final; publish_gate.py passes
- [x] Licence, name, ORCID in place
- [x] Evidence log row written the day of release
