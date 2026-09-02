# ShortageTrace

**Status:** released v0.1.0 (verified 2026-09-01) | **Maintainer:** A. Nwachukwu, PharmD, BCPS, ORCID 0000-0000-0000-0000
**Licence:** code MIT, data CC BY 4.0 | **DOI:** [pending first release]

> TEACHING FIXTURE for the Straight Green Card Profile Building Program. The persona
> is constructed and the data is synthetic. Nothing here is a real finding.

A longitudinal panel of national drug shortage episodes, 2015-2025, linked to product
and ingredient identifiers and therapeutic class.

Built because shortage data is published as a running list of current and resolved
records, which answers "what is short today" and cannot answer "how long do shortages
last, and which products keep going short". Turning a list into episodes is the work.

## What is here
```
code/    numbered scripts in run order
data/processed/  the panel, plus a product-level summary and qa_report.txt
docs/    CODEBOOK, LIMITATIONS, VERIFY_CHECKLIST, NEXT_STEPS
paper/   stats.json and sensitivity_gap_rule.json
```

## Headline numbers
All interpolated from `paper/stats.json`.

- **1,710 shortage episodes** across **880 products**, 2015-2025
- median episode **79 days**, 90th percentile **232 days**
- **53.6% of products** went short more than once
- **277 episodes** lasted over six months
- longest single episode **1122 days**
- heaviest class for long episodes: **Oncology** (27.7% of its episodes over 180 days)

## The one judgment that shapes everything
An episode ends when a product stops being listed for **30 days or more**.
Shorter gaps are treated as continuous, because below a month a relisting usually
reflects reporting cadence rather than genuine resupply.

That threshold is a parameter, not a constant. `paper/sensitivity_gap_rule.json`
reports the panel rebuilt at 14, 30 and 60 days. The median duration and the repeat
share are stable across all three, so the headline findings do not depend on the choice.

## Limitations
See `docs/LIMITATIONS.md`. In particular this dataset describes **reported** shortages,
which is not the same as experienced scarcity at any given hospital.

## Citation
See `CITATION.cff`.
