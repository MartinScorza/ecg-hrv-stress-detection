# Python / scikit-learn analysis

The academic report states that Google Colab and Python were used for complementary analysis and that the final decision tree was trained with **scikit-learn** using the reported time-domain HRV table.

The original `.py` or `.ipynb` source is **not present in the preserved project archive**.

## What can be stated from the report

The displayed tree uses splits based on:

- RMSSD, labelled `RMSS` in the original result table;
- minimum RR;
- mean RR.

The root node contains the twelve condition-level observations reported for six participants under two experimental conditions.

## What is not preserved

The following are not documented sufficiently to reconstruct the original training environment with certainty:

- original notebook/script;
- scikit-learn version;
- exact feature-selection code;
- train/test split, if any;
- cross-validation, if any;
- random seed;
- hyperparameter configuration;
- preprocessing code;
- original input spreadsheet/CSV.

No independent validation metrics are reported. The tree is therefore documented as an **exploratory fit to a small academic dataset**, not as a validated predictive model.

## Future work

If the original notebook can be recovered, it should be added here with its environment documented exactly.

If a new implementation is written instead, it must be clearly labelled as a **reconstruction** and kept separate from claims about the original project.
