# Results

This directory is reserved for publication-safe, reproducible outputs.

The preserved academic report contains time-domain and frequency-domain HRV tables for twelve condition-level observations from six participants.

## Verified descriptive observations from the report

For the six within-participant stress-versus-relaxation comparisons, the relaxation condition had:

- higher Mean RR in 6/6 comparisons;
- lower mean heart rate in 6/6 comparisons;
- higher RMSSD/`RMSS` in 6/6 comparisons;
- higher pRR50 in 6/6 comparisons.

Frequency-domain differences were less systematic across the participants.

These are descriptive observations from a very small academic sample. They are **not** presented as statistically validated effects, diagnostic performance, or evidence of generalization.

## Decision tree

The report includes an exploratory scikit-learn decision tree trained from the time-domain HRV table. The original Python source and independent validation procedure are not preserved.

No accuracy, sensitivity, specificity, F1-score, ROC-AUC, or external-validation metric is claimed by this repository.

## Publication rule

Participant-level tables, raw traces, and derived series should not be copied into this directory until the data-publication status has been explicitly verified. See [`../data/README.md`](../data/README.md).
