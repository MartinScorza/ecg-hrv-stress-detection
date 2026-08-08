# Data policy

The original project used ECG recordings acquired from human participants during experimentally assigned stress and relaxation conditions.

## Public repository policy

Raw physiological recordings are **not included** in this repository.

Do not publish any of the following without verifying appropriate consent, authorization, and applicable institutional rules:

- raw participant ECG;
- participant-level RR/NN series;
- acquisition timestamps or device metadata that could support re-identification;
- participant-code lookup tables;
- consent forms;
- private laboratory notes containing personal information;
- any hidden metadata linking files to participants.

The original report uses pseudonymous identifiers such as `Patient 1` to `Patient 6`. Pseudonymization should not be treated as proof of irreversible anonymization.

## Recommended reproducible examples

A future public demo should use one of these options:

1. **Synthetic ECG**, clearly marked as synthetic and generated only for demonstration/testing; or
2. **Public ECG data** from a dataset whose license explicitly allows the intended use and redistribution.

Any public example should document:

- source or generation method;
- license;
- sampling frequency;
- units;
- column format;
- preprocessing applied;
- whether R-peak annotations are reference labels or algorithm outputs.

## Original sample

The academic report describes six healthy student participants aged 20-24 years, each measured under two assigned experimental conditions. The reported condition labels are experimental task labels, not clinical diagnoses.
