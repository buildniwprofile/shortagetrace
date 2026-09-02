# Limitations — ShortageTrace

1. **Reported, not experienced.** This describes shortages as reported to a national
   database. A hospital can be unable to obtain a product that was never listed, and a
   listed product can be available locally. The gap between reporting and experience is
   the main thing this dataset does not measure.

2. **The episode boundary is a construct.** Real supply does not arrive with episode
   markers. The 30-day rule is defensible and it is still a rule. Sensitivity across
   14, 30 and 60 days is reported; use it.

3. **Right censoring.** Episodes open at the cutoff have no duration. Summaries of
   duration are conditional on resolution, which biases them downward for classes with
   long-running shortages.

4. **Product identity drifts.** Reformulations and relabelling can change the identifier
   while the clinical product stays the same, splitting one product's history into two.
   Not corrected in v0.1.0; listed in NEXT_STEPS.

5. **Class assignment is not always one-to-one.** Products with several classifications
   were assigned their primary class. Concurrency by class inherits that choice.

6. **No severity.** A shortage of one manufacturer's presentation and a shortage with no
   therapeutic alternative are the same row here. That is the largest missing dimension
   and it is the subject of the planned substitution-burden analysis.

7. **This cannot tell you whether patients were harmed.** It measures supply reporting.
