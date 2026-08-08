# Limitations

## Experimental sample

The project report describes six healthy student participants aged 20-24 years. Each participant contributed one stress-condition and one relaxation-condition observation.

This sample is too small to support clinical or population-level conclusions.

## Ground truth

`Stress = 1` and `Stress = 0` represent assigned experimental conditions, not clinical diagnoses and not independently validated physiological ground truth.

No independent clinical, psychometric or biochemical reference standard is documented in the recovered material.

## R-peak and NN processing

Several processing details remain insufficiently documented, including the exact selected-final-VI filter configuration, normalization, moving-window length and RR-to-NN correction method. These omissions limit reproducibility and may affect HRV estimates.

## LabVIEW execution status

The previously missing custom dependency `Global 1.vi` was recovered from a broader historical project backup and is now preserved in the repository.

This resolves the missing-file problem at the archive level, but it does **not** yet prove clean-environment execution. The three custom VIs still need to be opened together in a compatible LabVIEW environment to verify broken links, runtime controls and dependency compatibility.

A recovered `.lvproj` belongs to an older acquisition configuration and does not reference the selected final VI pair, so it is not used as evidence of a complete final project setup.

## Frequency-domain HRV

The report notes that frequency-domain differences were less systematic. Recording length, breathing, movement artifacts and inter-participant variability can affect spectral HRV interpretation.

The complete preprocessing of the irregular RR series before AR spectral analysis is still not preserved.

## Machine learning

The original scikit-learn notebook remains unavailable. A deep file scan of the recovered backup found no `.py` or `.ipynb` source for the reported decision tree.

No independent test set or cross-validation procedure is reported.

Because each participant contributed both experimental conditions, any future evaluation should keep all observations from one participant in the same fold. Participant-wise splitting is more appropriate than randomly splitting individual records when assessing generalization to unseen people.

## Data availability

Original ECG recordings and the final result workbook were recovered, but they contain participant names and other identifying information. They are retained only as private source evidence and are not distributed in the repository.

## Clinical scope

This project is an academic engineering proof of concept. It is not a medical device, is not clinically validated, and must not be used for diagnosis, treatment, monitoring or clinical decision-making.
