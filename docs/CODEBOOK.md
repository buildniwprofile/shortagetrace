# Codebook — ShortageTrace

| Column | Type | Definition | Source | Transformation |
|---|---|---|---|---|
| `episode_id` | text | Unique episode key | computed | sequential |
| `product_id` | text | Product identifier | product directory | none |
| `ingredient_id` | text | Active ingredient identifier | product directory | joined on product |
| `therapeutic_class` | text | Therapeutic class | classification reference | joined; see V5 |
| `dosage_form` | text | Dosage form | product directory | none |
| `episode_start` | date | First listing date in the episode | shortage database | earliest listing after a qualifying gap |
| `episode_end` | date | Last listing date | shortage database | blank where still open at cutoff |
| `duration_days` | integer | `episode_end - episode_start` | computed | **blank, not zero**, where open |
| `is_resolved` | 0/1 | Episode has a resolution date | shortage database | none |
| `is_open_at_cutoff` | 0/1 | Still listed at 2025-12-31 | computed | censoring flag |
| `recurrence_index` | integer | Count of prior episodes for this product | computed | 0 for first |
| `days_since_prior_episode` | integer | Gap to previous episode | computed | blank for first |
| `episode_gap_rule_days` | integer | The threshold used to build this panel | parameter | recorded per row so the rule travels with the data |

## Why the gap rule is a column
Every row carries the parameter that produced it. Anyone who re-runs the panel under
a different rule gets a file that says so. A dataset whose construction rule is only
in the README loses that rule the first time somebody copies the CSV.

## Open episodes are censored, not truncated
`duration_days` is blank where an episode was still active at the cutoff. Filling it
with the days-so-far would understate true duration and bias every summary downward.
