# Limitations

## Experimental sample

The report describes six healthy student participants aged 20-24 years. Each participant contributed a stress-condition and a relaxation-condition observation.

This sample is far too small to support clinical or population-level conclusions.

## Ground truth

`Stress = 1` and `Stress = 0` represent the assigned experimental condition, not a clinical diagnosis and not an independently validated physiological ground truth.

No independent clinical, psychometric, or biochemical reference standard is documented in the preserved archive.

## R-peak and NN processing

Several processing parameters are not preserved, including the exact filter design, normalization, moving-window length, and RR-to-NN correction method. These omissions limit reproducibility and may affect HRV estimates.

## LabVIEW dependency gap

`PARALLEL FINAL.vi` references both the preserved processing subVI and an additional file named `Global 1.vi`. The latter is absent from the original archive.

Its purpose and whether it is required to load or execute the final acquisition path are not known from binary inspection alone. Until it is recovered or inspected in LabVIEW, the preserved VIs should not be described as independently runnable in a clean environment.

## Frequency-domain HRV

The report itself notes that the frequency-domain differences were less systematic. Short recordings, breathing effects, movement artifacts, and inter-participant variability can strongly affect spectral HRV interpretation.

The RR-series preprocessing required before AR spectral analysis is not fully documented.

## Machine learning

The original scikit-learn notebook is missing. No independent test set or cross-validation procedure is reported.

Because the same participant contributed both experimental conditions, any future validation should avoid placing one condition from a participant in training and the other in testing. Participant-wise splitting is more appropriate for assessing generalization to unseen people.

## Clinical scope

This project is an academic engineering proof of concept. It is not a medical device, is not clinically validated, and must not be used for diagnosis, treatment, monitoring, or clinical decision-making.
