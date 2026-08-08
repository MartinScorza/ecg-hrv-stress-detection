# Recovered project archive audit

A broader BM04 project backup was recovered after the initial portfolio audit. This document records what was found, what was useful for verification, and what was intentionally excluded from the recruiter-facing repository.

## What the backup added

The recovered archive contains substantially more material than the initially supplied final-project ZIP, including:

- 13 LabVIEW VIs;
- one LabVIEW project file plus local project configuration files;
- original ECG acquisition recordings;
- result spreadsheets and CSV exports;
- report and presentation PDFs;
- MATLAB Pan-Tompkins reference material;
- participant metadata files.

The complete backup is **not suitable for direct publication** because it mixes code, historical versions, third-party material and identifiable human physiological data.

## Final LabVIEW selection

The initially supplied portfolio archive already contained a clear final pair:

- `PARALLEL FINAL.vi`
- `Processing_data_subvi_V23.vi`

The broader backup confirmed that these files belong to a larger development history and also recovered `Global 1.vi`, a custom dependency referenced by the main VI.

The repository therefore preserves:

```text
PARALLEL FINAL.vi
Processing_data_subvi_V23.vi
Global 1.vi
```

Older acquisition, processing and `while true` variants remain excluded from the main repository. Keeping every historical VI would make the portfolio harder to understand and could falsely imply that all versions are required to run the final workflow.

## Legacy LabVIEW project

The recovered `ACAUISITION.lvproj` references an older acquisition VI and `Global 1.vi`. It does not reference the selected final VI pair.

It is therefore useful as historical environment evidence, but it is not presented as the final project definition.

The project XML reports `LVVersion="23008000"`. That value is not used to claim the exact save version of the selected final VIs.

## Acquisition data verification

The recovered condition recordings contain explicit timestamps.

Across the principal stress and relaxation recordings inspected:

- timestamp interval: **0.002 s**;
- corresponding sampling frequency: **500 Hz**;
- recording duration: approximately **306-381 s**.

This independently confirms the 500 Hz sampling frequency documented in the academic report.

## Final result table verification

The recovered final workbook contains the same twelve condition-level HRV rows shown in the report, including an anonymized `Patient 1` through `Patient 6` section.

The workbook also contains a named internal section, so the original file is not redistributed.

A unit ambiguity was resolved from the formulas:

- an intermediate mean-heart-rate value is stored in Hz;
- the report-facing table multiplies it by 60;
- the final value is reported in bpm.

A two-row aggregate summary derived from the anonymized final table is included in `results/aggregate_hrv_summary.csv`.

## Python / machine-learning search

A full extension and filename scan of the recovered backup found no:

- `.py` file;
- `.ipynb` notebook;
- preserved scikit-learn training source.

The decision-tree implementation therefore remains report-documented rather than source-reproducible.

## MATLAB reference code

The recovered backup contains a MATLAB Pan-Tompkins implementation by Hooman Sedghamiz and an accompanying BSD-style license.

This material is third-party reference/testing code. It is not presented as the team's implementation and is intentionally excluded from the main source tree.

A local MATLAB helper script also contains a machine-specific absolute path, which further supports treating that folder as historical working material rather than polished project source.

## Privacy findings

The recovered archive contains direct identifiers associated with physiological recordings, including:

- participant names in filenames;
- metadata files with names;
- direct numeric identifiers;
- acquisition timestamps;
- participant-level ECG and results.

For that reason:

- the original recordings are not committed;
- the original result workbook is not committed;
- participant metadata files are not committed;
- the complete recovered ZIP must not be published.

Only publication-safe aggregate results are carried into the portfolio repository.

## Publication decisions

| Material | Portfolio decision |
|---|---|
| Selected final main VI | Include |
| Selected final processing VI | Include |
| Recovered `Global 1.vi` | Include |
| Historical LabVIEW variants | Exclude |
| Legacy `.lvproj` / aliases | Exclude; document only |
| Original human ECG | Exclude |
| Original result workbook | Exclude |
| Aggregate anonymized statistics | Include |
| Original Python notebook | Not found |
| Third-party MATLAB Pan-Tompkins | Exclude; document attribution |
| Academic report / presentation | Exclude from source tree by default |

## Remaining technical work

The archive search is complete enough for portfolio publication, but it does not replace runtime verification. The remaining engineering tasks are:

1. open the three preserved custom VIs together in LabVIEW;
2. check for broken links and missing NI components;
3. document final front-panel/runtime parameters;
4. identify the exact acquisition hardware if available;
5. determine the RR-to-NN correction logic from the block diagram;
6. recover the original Python/Colab code only if it exists outside this backup;
7. create a synthetic or public-data demo if end-to-end reproducibility is desired.
