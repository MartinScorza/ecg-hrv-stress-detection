# Python / scikit-learn analysis

The academic report states that Google Colab and Python were used for complementary analysis and that the final decision tree was trained with **scikit-learn** using the reported time-domain HRV table.

The original training source is still unavailable.

A broader BM04 backup was recovered and scanned recursively across all files. The scan found **no `.py` file and no `.ipynb` notebook** containing the reported scikit-learn analysis.

This means the missing source is not simply hidden elsewhere in the recovered project ZIP; if it still exists, it is likely stored outside this backup, for example in the original Google Colab account or another personal archive.

## What can be stated from the preserved results

The displayed tree uses splits based on:

- RMSSD, labelled `RMSS` in the original result table;
- minimum RR;
- mean RR.

The root node contains the twelve condition-level observations reported for six participants under two experimental conditions.

The recovered final results workbook confirms the input table used for the report, but it does not contain the Python training code.

## What is not preserved

The following cannot be attributed to the original implementation with certainty:

- original notebook/script;
- scikit-learn version;
- exact feature-selection code;
- train/test split, if any;
- cross-validation, if any;
- random seed;
- hyperparameter configuration;
- preprocessing code.

No independent validation metrics are reported. The tree is therefore documented as an **exploratory fit to a small academic dataset**, not as a validated predictive model.

## Reconstruction policy

A future Python reimplementation could improve reproducibility, but it must be labelled clearly as a **reconstruction** rather than presented as the missing original source.

If the original Colab notebook is eventually recovered, it should be audited first and then added separately with its actual package versions and execution assumptions.
