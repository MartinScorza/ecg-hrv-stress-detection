# Privacy and ethics

## Human physiological data

The original experiment involved ECG recordings from human participants. ECG, RR/NN series, and derived HRV measurements are physiological data and should be treated conservatively even when direct identifiers are removed.

The academic report uses pseudonymous labels (`Patient 1` through `Patient 6`) and describes the participants as healthy university students aged 20-24 years. Pseudonymization is not equivalent to demonstrated irreversible anonymization.

## Repository publication policy

The following are excluded from public release unless rights and consent are explicitly verified:

- raw ECG recordings;
- participant-level RR/NN files;
- acquisition timestamps and identifying metadata;
- participant-code lookup tables;
- consent or ethics documentation containing personal information;
- private laboratory notes.

Publication-safe demonstrations should use synthetic ECG or appropriately licensed public data.

## Experimental labels

The labels `stress` and `relaxation` correspond to assigned task conditions. They do not constitute clinical diagnoses or validated psychological ground truth.

## Clinical disclaimer

This work is an academic proof of concept and must not be used for diagnosis, treatment, patient monitoring, or clinical decision-making.
