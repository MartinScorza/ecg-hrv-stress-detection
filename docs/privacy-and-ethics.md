# Privacy and ethics

## Human physiological data

The original experiment involved ECG recordings from human participants. ECG, RR/NN series and derived HRV measurements are physiological data and should be treated conservatively even when obvious identifiers are removed.

The academic report uses pseudonymous labels (`Patient 1` through `Patient 6`) and describes the participants as healthy university students aged 20-24 years. Pseudonymization is not equivalent to demonstrated irreversible anonymization.

## Findings from the recovered backup

A broader project archive was later recovered and inspected privately. It confirms that the working files were **not fully anonymous**.

The source material contains combinations of:

- participant names in filenames;
- metadata text files containing names;
- direct numeric personal identifiers;
- acquisition timestamps;
- raw ECG recordings;
- participant-level result files;
- a result workbook containing both named and pseudonymized versions of the final table.

For this reason, the recovered ZIP itself must not be published as a repository asset.

## Repository publication policy

The following remain outside the repository:

- raw human ECG recordings;
- participant-level RR/NN files;
- original participant-level result spreadsheets;
- acquisition metadata carrying identifiers;
- participant-code or participant-name lookup information;
- consent or ethics documents containing personal information;
- private laboratory notes.

The repository includes only publication-safe aggregate statistics derived from the final anonymized result table.

Any future executable demonstration should use synthetic ECG or appropriately licensed public data unless explicit authorization for the original recordings is established.

## Data minimization

The portfolio does not need raw human data to demonstrate the engineering work. The useful evidence can be shown through:

- preserved source code;
- architecture and methodology documentation;
- aggregate results;
- synthetic/public demonstration signals;
- publication-safe figures produced from non-identifiable data.

This reduces privacy risk without weakening the technical story of the project.

## Experimental labels

The labels `stress` and `relaxation` correspond to assigned task conditions. They do not constitute clinical diagnoses or validated psychological ground truth.

## Clinical disclaimer

This work is an academic proof of concept and must not be used for diagnosis, treatment, patient monitoring or clinical decision-making.
