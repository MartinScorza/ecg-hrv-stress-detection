# LabVIEW implementation

This directory preserves the two LabVIEW VIs available in the original project archive **without functional modification or renaming**.

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

## Required environment

The exact original LabVIEW version is not preserved. Reproduction is expected to require, at minimum:

- a compatible LabVIEW installation;
- NI-DAQmx;
- NI signal-processing functionality used by the VIs;
- the NI Time Series Analysis / Advanced Signal Processing components referenced by the processing VI;
- compatible NI acquisition hardware for live acquisition.

## Reproducibility gaps

The binary VIs preserve implementation artifacts but do not, by themselves, document all runtime configuration. The following still require recovery or visual inspection in the original LabVIEW environment:

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
