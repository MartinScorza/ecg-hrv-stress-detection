# Results

This directory contains publication-safe summaries derived from the final project results.

A broader project backup recovered the original workbook used to prepare the report tables. The workbook contains the final twelve condition-level observations for six participants and reproduces the anonymized `Patient 1` through `Patient 6` values shown in the academic report.

The workbook itself is **not published** because another section of the same file retains participant names.

## Aggregate HRV summary

[`aggregate_hrv_summary.csv`](aggregate_hrv_summary.csv) contains arithmetic means calculated from the final anonymized twelve-row table, grouped by assigned experimental condition.

The file contains only two aggregate rows:

- stress, `n = 6`;
- relaxation, `n = 6`.

It includes Mean RR, RMSSD, pRR50, mean heart rate and LF/HF.

These values are descriptive summaries of a very small academic sample. They are not effect estimates, diagnostic metrics, population norms or evidence of generalization.

## Final within-participant observations

For the six stress-versus-relaxation comparisons in the final table, the relaxation condition had:

- higher Mean RR in 6/6 comparisons;
- lower mean heart rate in 6/6 comparisons;
- higher RMSSD/`RMSS` in 6/6 comparisons;
- higher pRR50 in 6/6 comparisons.

Frequency-domain differences were less systematic across participants.

## Mean heart-rate unit check

The recovered workbook clarifies a unit ambiguity in older exported tables:

- an intermediate `HR Mean` field is stored in Hz;
- the report-facing table multiplies that field by 60;
- the resulting bpm values agree with `60000 / Mean RR [ms]`.

## Decision tree

The report includes an exploratory scikit-learn decision tree derived from the time-domain HRV table. A deep scan of the recovered project backup found no original `.py` or `.ipynb` source for the model.

No independent validation accuracy, sensitivity, specificity, F1-score, ROC-AUC or external-validation metric is claimed by this repository.

## Publication boundary

Raw traces, participant-level result tables and the original workbook remain outside the repository because the recovered source material contains identifying information. See [`../data/README.md`](../data/README.md).
