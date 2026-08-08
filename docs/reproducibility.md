# Reproducibility status

## Current status

The recovered project backup improves the evidence base substantially, but the original workflow is **not yet reproducible end to end in a clean environment**.

The key change from the initial audit is that several artifacts previously thought to be missing have now been recovered and inspected privately.

## Preserved in the repository

- `labview/PARALLEL FINAL.vi`
- `labview/Processing_data_subvi_V23.vi`
- `labview/Global 1.vi`
- methodology and limitations documentation
- publication-safe aggregate HRV summary

The final main VI and processing subVI are byte-for-byte identical to the files originally supplied for this portfolio reconstruction. `Global 1.vi` is preserved byte-for-byte from the broader recovered project backup.

## Recovered privately but not redistributed

The broader backup contains:

- original human ECG recordings;
- multiple stress and relaxation acquisition files;
- the result workbook used to prepare the final report tables;
- older LabVIEW acquisition and processing variants;
- a legacy LabVIEW `.lvproj`;
- presentation/report material;
- a third-party MATLAB Pan-Tompkins implementation with its own BSD-style license.

The human recordings and original workbook are not committed because the archive contains participant names and some files contain direct numeric identifiers.

## Acquisition evidence recovered

The main stress/relaxation CSV recordings use timestamps separated by **0.002 s**, independently confirming a **500 Hz sampling rate**.

The principal condition recordings inspected span approximately **306-381 s**. This is consistent with an approximately five-minute protocol with variation or acquisition overhead.

Some acquisition files contain two columns (`signal`, `time`) while later variants contain three columns, with an additional zero-valued channel/field. The exact export schema should be documented before attempting automated reuse.

## LabVIEW dependency relationship

Binary inspection supports:

```text
PARALLEL FINAL.vi
    -> Processing_data_subvi_V23.vi
    -> Global 1.vi
```

The main VI contains references to both custom dependencies. The recovered `Global 1.vi` was found in a historical folder of the broader backup and is now preserved with the final pair.

A recovered legacy project file identifies `AQUIISITON.vi` and `Global 1.vi` and reports `LVVersion="23008000"`. This helps date the project environment, but the `.lvproj` does not reference the selected final VI pair, so it is not treated as a runnable final project definition.

## Results workbook recovered

`Resultats_2_0 - copia.xlsx` contains the 12 final condition-level rows used in the report. One section retains participant names, while a second section reproduces the same values using `Patient 1` through `Patient 6`.

The workbook also resolves a unit ambiguity:

- the intermediate `HR Mean` field is stored in Hz;
- the report-facing sheet multiplies it by 60 to obtain bpm;
- the bpm values agree with `60000 / Mean RR [ms]`.

The workbook itself is not redistributed because it retains named participant-level data. A safe aggregate derived from the anonymized table is provided in `results/aggregate_hrv_summary.csv`.

## Still missing or unresolved

- original Google Colab/Jupyter notebook;
- original Python script;
- exact Python environment and package versions;
- exported R-peak indices/timestamps;
- exported RR series;
- corrected NN series;
- exact RR-to-NN artifact-correction algorithm;
- exact runtime configuration for the selected final VI pair;
- exact NI acquisition-card model and device/channel mapping;
- clean-environment execution of the recovered LabVIEW dependency set;
- complete spectral preprocessing details before AR estimation.

A deep file scan of the recovered backup found **no `.py` or `.ipynb` file** containing the scikit-learn analysis.

## Python status

The academic report explicitly documents Google Colab, Python and scikit-learn for the decision tree. No source file for that analysis was recovered.

`requirements.txt` therefore remains intentionally minimal rather than guessing the original environment.

## What can now be independently checked

From the recovered files and report tables:

- 500 Hz sampling is confirmed from timestamp spacing;
- recording durations can be measured directly from the source files;
- `HR mean [bpm] = 60000 / Mean RR [ms]` is confirmed by the report-facing workbook;
- LF/HF is consistent with reported LF and HF values;
- normalized LF and HF values are consistent with normalization over LF + HF;
- the displayed decision-tree structure remains consistent with the final time-domain table, although the original notebook is absent.

## Next reproducibility steps

1. Open the three preserved custom VIs together in a compatible LabVIEW environment.
2. Record any remaining missing dependencies and broken links.
3. Document all front-panel controls and acquisition parameters for the selected final pair.
4. Identify the exact NI hardware model and channel configuration if still available.
5. Document the RR-to-NN correction procedure from the block diagram, if implemented there.
6. Recover the original Python/Colab analysis if it exists elsewhere.
7. Add a synthetic or suitably licensed public ECG demo rather than publishing human recordings.
8. Validate R-peak detection against reference annotations on publication-safe data.
9. If the ML analysis is extended, evaluate by participant rather than randomly splitting paired records from the same participant.
