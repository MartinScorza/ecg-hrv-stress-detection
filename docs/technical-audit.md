# Technical audit summary

This audit separates what is preserved in the final LabVIEW files, what was recovered from the broader project backup, what is documented only in the academic material, and what still cannot be reproduced.

## Selected final LabVIEW artifacts

### `PARALLEL FINAL.vi`

Internal references support:

- NI-DAQmx analog-voltage channel creation;
- sample-clock configuration;
- acquisition start/read/stop/clear sequence;
- single-channel multi-sample acquisition;
- spreadsheet-style export;
- invocation of `Processing_data_subvi_V23.vi`;
- use of `Global 1.vi`.

### `Processing_data_subvi_V23.vi`

Internal references support:

- Butterworth filtering;
- derivative calculation;
- moving-average processing;
- peak detection;
- mean and standard-deviation calculation;
- autoregressive spectrum estimation;
- delimited-spreadsheet reading.

The presence of a dependency confirms that the VI references the function; it does not by itself establish every runtime parameter or prove every possible code path was executed during the reported experiments.

## Recovered custom dependency

A broader project backup contains `Global 1.vi`, matching the custom dependency name referenced by the main final VI. It is now preserved in `labview/` without modification.

The recovered file was stored in a historical backup folder, so its compatibility with the selected final VI pair still needs to be tested in LabVIEW. The repository preserves the original file rather than attempting to recreate a replacement.

## Binary integrity

Git blob identifiers:

- `PARALLEL FINAL.vi`: `4adf9b39acf3373edde3e401173f4ff525684492`
- `Processing_data_subvi_V23.vi`: `3cf479c0688823048d6bf254d51374685f198877`
- `Global 1.vi`: `4ed050e66bd5fd469ed971a8b13f8174dfaa7975`

These hashes document preservation integrity, not successful runtime execution.

## Broader backup inventory

The recovered backup contains 13 LabVIEW VIs in total, including acquisition-only versions, processing variants, `con while true` variants and separate Pan-Tompkins experiments. It also contains:

- one legacy `.lvproj`;
- original ECG recordings;
- result spreadsheets and CSV exports;
- three project PDFs;
- two MATLAB scripts plus a MATLAB sample file;
- participant metadata files.

The historical variants are intentionally not copied into the recruiter-facing repository because the initially supplied portfolio archive already identified the selected final main VI and processing subVI.

## Sampling and recording verification

The recovered `Oficial tests` condition recordings contain regularly spaced timestamps with:

`delta t = 0.002 s`

which independently verifies:

`sampling frequency = 500 Hz`

The main stress and relaxation recordings inspected have durations of roughly 306-381 s.

## Results verification

The recovered final workbook reproduces the 12 anonymized rows shown in the report as `Patient 1` through `Patient 6`.

It also contains an internal named version of the same final table, which is why the workbook is not redistributed publicly.

The workbook clarifies that the intermediate `HR Mean` values are stored in Hz. The report-facing table applies a factor of 60 and reports bpm. Those bpm values agree with `60000 / Mean RR [ms]`.

A publication-safe aggregate derived from the final anonymized table is committed under `results/`.

## Pan-Tompkins reference material

The broader backup contains a MATLAB implementation named `pan_tompkin.m` by Hooman Sedghamiz. The file identifies itself as a complete Pan-Tompkins implementation and carries a BSD-style license.

This code is treated as third-party reference/testing material. It is **not** evidence that the project's LabVIEW detector implemented every adaptive threshold, search-back or T-wave discrimination step from that MATLAB version, and it is not redistributed as team-authored source code.

A small local MATLAB script also contains an absolute development path, reinforcing the decision not to publish the historical MATLAB folder as project source.

## Legacy LabVIEW project file

The recovered `ACAUISITION.lvproj` references `AQUIISITON.vi` and `Global 1.vi`, not the selected final VI pair. It reports `LVVersion="23008000"`.

This is useful historical evidence but is not presented as the final executable project configuration.

## Still unavailable or unresolved

- original `.py` or `.ipynb` source for the decision tree;
- exact Python environment;
- exported R-peak indices/timestamps;
- exported RR and corrected NN series;
- exact RR-to-NN correction method;
- exact selected-final-VI runtime controls;
- exact NI hardware model and channel mapping;
- complete preprocessing sequence before AR spectrum estimation;
- independent machine-learning validation results.

## Privacy findings

The recovered archive contains human ECG files whose filenames include participant names. Separate metadata text files also contain names and direct numeric identifiers.

Those files must remain outside the public repository. The full recovered ZIP should not be published.

## Claim policy

The repository must not state or imply:

- validated stress diagnosis;
- medical-device status;
- clinically validated monitoring;
- generalizable model accuracy;
- sole authorship of collaborative work;
- end-to-end reproducibility until the preserved dependency set has actually been opened and tested in LabVIEW.
