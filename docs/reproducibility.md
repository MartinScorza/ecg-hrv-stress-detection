# Reproducibility status

## Current status

The original project **cannot currently be reproduced end-to-end** from the preserved archive alone.

This is not hidden: preserving the distinction between available evidence and missing artifacts is part of the repository design.

## Preserved source artifacts

- `labview/PARALLEL FINAL.vi`
- `labview/Processing_data_subvi_V23.vi`
- methodology and results documented in the original academic report

The two LabVIEW files committed to the repository are byte-for-byte identical to the VIs in the original ZIP.

## LabVIEW dependency relationship

Binary inspection supports the following relationship:

```text
PARALLEL FINAL.vi
    -> Processing_data_subvi_V23.vi
```

The main VI contains two references to the processing subVI. The processing subVI does not contain a reciprocal reference to the main VI. Both files are therefore retained as distinct project artifacts.

The main VI also references **`Global 1.vi`**, which is not present in the original ZIP. Its purpose and runtime necessity remain unresolved. A clean LabVIEW load may therefore require manual dependency resolution before the original workflow can execute.

## Missing original artifacts

- `Global 1.vi`, referenced by the main VI;
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

In addition, `PARALLEL FINAL.vi` references the unavailable `Global 1.vi`. The repository does not attempt to recreate this missing dependency without evidence of its original contents.

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

1. Open `PARALLEL FINAL.vi` in a compatible LabVIEW environment and determine the purpose of the unresolved `Global 1.vi` reference.
2. Recover `Global 1.vi` if it belongs to the original project and can be shared.
3. Recover the original Python/Colab analysis if available.
4. Recover the original exported result spreadsheet.
5. Document every LabVIEW runtime control and processing parameter.
6. Record the NI hardware model and DAQ channel configuration.
7. Document the RR-to-NN correction procedure.
8. Add a synthetic or appropriately licensed public ECG example.
9. Validate R-peak detection against reference annotations on a publication-safe dataset.
10. If the ML analysis is extended, evaluate by participant rather than randomly splitting paired records from the same participant.
