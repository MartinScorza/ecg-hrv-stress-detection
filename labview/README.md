# LabVIEW implementation

This directory preserves the two LabVIEW VIs available in the original project archive **without functional modification or renaming**.

## File relationship

The two files are not duplicates and serve different roles.

- `PARALLEL FINAL.vi` is the main acquisition/orchestration VI. Its internal dependency table contains two references to `Processing_data_subvi_V23.vi`.
- `Processing_data_subvi_V23.vi` is a separate processing subVI. It does not contain a reciprocal reference to `PARALLEL FINAL.vi`.

This supports preserving **both files** together. Without opening the block diagram in a compatible LabVIEW environment, the binary inspection cannot prove that the processing subVI executes on every possible runtime path, but it is clearly referenced by the main VI and belongs to the preserved project dependency set.

## Files

### `PARALLEL FINAL.vi`

The VI contains references to NI-DAQmx functionality for:

- analog-input voltage channel creation;
- sample-clock timing;
- task start;
- multi-sample, single-channel analog read;
- task stop and cleanup;
- spreadsheet-style export;
- execution of `Processing_data_subvi_V23.vi`.

Verified referenced NI functions include:

- `DAQmx Create Channel (AI-Voltage-Basic).vi`
- `DAQmx Timing (Sample Clock).vi`
- `DAQmx Start Task.vi`
- `DAQmx Read (Analog 1D DBL 1Chan NSamp).vi`
- `DAQmx Stop Task.vi`
- `DAQmx Clear Task.vi`
- `Write To Spreadsheet File (DBL).vi`

The original file name is retained because changing a LabVIEW VI name may affect subVI references.

#### Unresolved custom dependency

Binary inspection also found a reference to **`Global 1.vi`** in `PARALLEL FINAL.vi`. This file is not present in the original project ZIP.

`Global 1.vi` is therefore treated as an **unresolved dependency**. Its purpose, whether it is required on the final execution path, and whether it contains project-specific state must be confirmed by opening the main VI in a compatible LabVIEW environment. The repository does not fabricate or replace this missing file.

### `Processing_data_subvi_V23.vi`

The preserved processing VI references functionality including:

- `Butterworth Filter.vi`
- `Derivative x(t).vi`
- `TSA Moving Average.vi`
- `Peak Detector.vi`
- `Mean.vi`
- `Std Deviation and Variance.vi`
- `TSA AR Spectrum.vi`
- `Read Delimited Spreadsheet.vi`

The VI also references NI analysis libraries including `NI_AdvSigProcTSA.lvlib`.

No additional custom external VI was identified from the printable dependency strings of this processing file.

## Integrity verification

The two files committed to this repository were compared with the VIs in the original project ZIP. Their contents are byte-for-byte identical.

Git blob identifiers for the preserved binaries are:

- `PARALLEL FINAL.vi`: `4adf9b39acf3373edde3e401173f4ff525684492`
- `Processing_data_subvi_V23.vi`: `3cf479c0688823048d6bf254d51374685f198877`

These identifiers are included as an integrity record, not as evidence that the VIs have been successfully executed in a clean LabVIEW installation.

## Required environment

The exact original LabVIEW version is not preserved. Reproduction is expected to require, at minimum:

- a compatible LabVIEW installation;
- NI-DAQmx;
- NI signal-processing functionality used by the VIs;
- the NI Time Series Analysis / Advanced Signal Processing components referenced by the processing VI;
- compatible NI acquisition hardware for live acquisition;
- recovery or resolution of the missing `Global 1.vi` reference if LabVIEW requires it when loading or executing the main VI.

## Reproducibility gaps

The binary VIs preserve implementation artifacts but do not, by themselves, document all runtime configuration. The following still require recovery or visual inspection in the original LabVIEW environment:

- purpose and runtime requirement of `Global 1.vi`;
- exact NI hardware model and device/channel mapping;
- input voltage range and terminal configuration;
- acquisition duration and buffer settings;
- exact Butterworth filter parameters;
- normalization formula;
- moving-window length;
- threshold scaling;
- RR-to-NN artifact-correction logic;
- exact AR-spectrum preprocessing and settings;
- local export paths.

No changes should be made to the functional VIs until these settings are documented and a known-working baseline is preserved.
