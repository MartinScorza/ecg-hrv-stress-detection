# Data policy

The project used ECG recordings acquired from human participants during experimentally assigned stress and relaxation conditions.

A broader project backup has now been recovered and audited. It contains the original physiological recordings and related metadata, but those source files are **not distributed in this repository**.

## Why the original recordings are excluded

The recovered archive contains:

- raw ECG recordings;
- filenames containing participant names;
- metadata text files containing direct personal identifiers;
- acquisition timestamps;
- participant-level result files;
- a result workbook that includes both named and pseudonymized tables.

Because these files combine physiological data with identifying information, the complete recovered ZIP must not be published as a GitHub artifact.

Removing names from filenames alone would not be enough to establish that the source data are safe for unrestricted redistribution.

## What is safe to publish here

This repository may contain:

- aggregate statistics that do not identify individual participants;
- synthetic ECG generated for demonstration or testing;
- appropriately licensed public ECG data;
- code and documentation that do not embed participant information.

A publication-safe aggregate derived from the final anonymized result table is available in [`../results/aggregate_hrv_summary.csv`](../results/aggregate_hrv_summary.csv).

## Reproducible demo data

A future executable demo should preferably use either:

1. **synthetic ECG**, clearly labelled as synthetic; or
2. **public ECG data** whose license permits the intended use and redistribution.

Any public example should document:

- source or generation method;
- license;
- sampling frequency;
- units;
- column format;
- preprocessing applied;
- whether R-peak annotations are reference labels or algorithm outputs.

## Original sample

The academic report describes six healthy student participants aged 20-24 years, each measured under two assigned experimental conditions. The condition labels describe the experimental protocol, not a clinical diagnosis.

The recovered source files independently confirm the reported 500 Hz acquisition through their 0.002 s timestamp spacing. This technical verification does not change the privacy boundary: the original recordings remain private source material.
