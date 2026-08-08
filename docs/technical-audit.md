# Technical audit summary

This audit records the evidence boundary used for the portfolio repository. It distinguishes what is preserved in executable LabVIEW artifacts, what is described only in the academic report, and what remains unavailable.

## Preserved in LabVIEW artifacts

### `PARALLEL FINAL.vi`

References support:

- NI-DAQmx analog-voltage channel creation;
- sample-clock configuration;
- acquisition start/read/stop/clear sequence;
- single-channel multi-sample acquisition;
- spreadsheet-style export;
- invocation of the processing subVI.

### `Processing_data_subvi_V23.vi`

References support:

- Butterworth filtering;
- derivative calculation;
- moving-average processing;
- peak detection;
- mean and standard-deviation calculation;
- autoregressive spectrum estimation;
- delimited-spreadsheet reading.

The presence of these references demonstrates that the functions are dependencies of the VIs. It does not, by itself, establish every runtime parameter or prove every code path was executed during the reported experiments.

## Described in the report but not fully recoverable from the available source

- 500 Hz acquisition;
- NL 844 AC preamplifier and reported analog gains;
- 150 Hz analog low-pass cutoff;
- approximately 5-15 Hz QRS-focused digital filtering;
- fixed normalized threshold of 80;
- RR-to-NN artifact filtering;
- AR order 16 and Burg-Lattice configuration;
- Google Colab / scikit-learn decision-tree training;
- six participants and twelve condition-level observations;
- reported time- and frequency-domain HRV tables.

These elements are documented as historical project methods/results but are not all reproducible from the two binary VIs alone.

## Not available in the archive

- raw ECG data;
- original result spreadsheet;
- R-peak exports;
- RR/NN exports;
- Python or notebook source;
- exact Python environment;
- complete DAQ runtime configuration;
- complete LabVIEW parameter documentation;
- independent ML validation results.

## Claim policy

The repository must not state or imply:

- validated stress diagnosis;
- medical-device status;
- clinically validated monitoring;
- generalizable model accuracy;
- sole authorship of the collaborative project;
- reproducibility of outputs that cannot currently be regenerated from the preserved files.
