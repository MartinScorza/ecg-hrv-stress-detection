# Licensing

## Repository license

The repository is released under the [MIT License](../LICENSE).

The project was originally developed by a three-person academic team. The MIT License applies to material distributed in this repository; it does not change the license terms of external software, hardware drivers, datasets, publications or third-party source code referenced during the project.

## National Instruments dependencies

The LabVIEW VIs reference National Instruments software components, including NI-DAQmx and signal/time-series analysis functions. These dependencies are not redistributed here and remain subject to National Instruments licensing terms.

## Recovered `Global 1.vi`

A broader project backup recovered `Global 1.vi`, matching the custom dependency name referenced by the selected main LabVIEW VI. The original recovered binary is now preserved in `labview/`.

Its presence resolves the archive-level missing dependency, but the three custom VIs have not yet been tested together in a clean LabVIEW installation.

## Third-party Pan-Tompkins reference code

The broader backup also contains `pan_tompkin.m`, a MATLAB implementation by Hooman Sedghamiz. The source file and accompanying license identify it as third-party BSD-style licensed code.

That MATLAB folder is intentionally **not redistributed as team-authored project source** and is not used to claim that the LabVIEW implementation contains every feature of the third-party implementation.

If it is ever added for historical reference, its original copyright notice, license and authorship must be preserved clearly and separately from the project code.

## Academic report and figures

The original academic report and presentation are not included in the repository. They contain institutional material, participant-level results and figures from external sources. References are documented separately where useful, but third-party figures should not be redistributed without checking their source licenses.

## Human physiological data

Original participant ECG recordings and the complete recovered result workbook are not distributed. The recovered source archive contains identifying information, and the MIT License does not grant rights to underlying human-subject data stored outside this repository.

Any future synthetic or public dataset added to `data/` should include its own provenance and licensing information.
