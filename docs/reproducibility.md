# Reproducibility status

## Current status

The original project **cannot currently be reproduced end-to-end** from the preserved archive alone.

This is not hidden: preserving the distinction between available evidence and missing artifacts is part of the repository design.

## Preserved source artifacts

- `labview/PARALLEL FINAL.vi`
- `labview/Processing_data_subvi_V23.vi`
- methodology and results documented in the original academic report

## Missing original artifacts

- raw ECG recordings;
- exported filtered ECG;
- R-peak indices/timestamps;
- RR series;
- corrected NN series;
- original Excel/CSV result table;
- Google Colab/Jupyter notebook;
- Python script;
- exact Python environment;
- LabVIEW project file, if one existed;
- exact DAQ configuration;
- exact filter/MWI/normalization parameters;
- documented RR-to-NN artifact-correction algorithm.

## Dependency status

### LabVIEW

Verified references in the VIs indicate a need for:

- LabVIEW compatible with the preserved VIs;
- NI-DAQmx;
- NI signal-processing components;
- NI Time Series Analysis / Advanced Signal Processing functionality.

Exact version numbers are not preserved.

### Python

The report explicitly documents:

- Python through Google Colab;
- scikit-learn for the decision tree.

No other Python package is listed here as an original dependency unless it can be verified from recovered source code.

## What can be independently checked from the report

- `HR mean = 60000 / Mean RR` is internally consistent with the reported table values;
- LF/HF is consistent with reported LF and HF values;
- normalized LF and HF values are consistent with normalization over LF + HF;
- the displayed decision-tree structure is consistent with the published time-domain table, but this does not replace the missing original notebook.

## Path to improved reproducibility

1. Recover the original Python/Colab analysis if available.
2. Recover the original exported result spreadsheet.
3. Open both VIs in a compatible LabVIEW environment and document every runtime control and processing parameter.
4. Record the NI hardware model and DAQ channel configuration.
5. Document the RR-to-NN correction procedure.
6. Add a synthetic or appropriately licensed public ECG example.
7. Validate R-peak detection against reference annotations on a publication-safe dataset.
8. If the ML analysis is extended, evaluate by participant rather than randomly splitting paired records from the same participant.
