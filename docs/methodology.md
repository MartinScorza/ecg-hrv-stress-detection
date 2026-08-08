# Signal-processing and HRV methodology

This document separates methods described in the academic report from implementation details that can be supported by the preserved LabVIEW VIs.

## 1. R-peak processing

The report describes a Pan-Tompkins-style chain:

1. band-pass filtering around the QRS-dominant frequency range, described as approximately 5-15 Hz;
2. second-order central differentiation;
3. squaring;
4. moving-window integration (MWI);
5. thresholding;
6. R-peak localization with LabVIEW `Peak Detector`.

The preserved processing VI references Butterworth filtering, derivative calculation, moving-average processing, and peak detection.

### Important implementation distinction

The report introduces the classical Pan-Tompkins method with adaptive thresholding, but the project implementation is described as using a **normalized ECG and a fixed threshold of 80** across recordings.

The preserved documentation does not demonstrate the full classical adaptive Pan-Tompkins logic such as signal/noise level updates, dual thresholds, search-back, or T-wave discrimination. The implementation is therefore described conservatively as **Pan-Tompkins-style**.

## 2. RR and NN intervals

R-peak locations were used to derive consecutive RR intervals.

The report states that RR intervals were filtered to remove artifacts or abnormal beats before obtaining NN intervals. However, the preserved files do not document:

- artifact-rejection thresholds;
- ectopic-beat detection;
- outlier rules;
- interpolation method;
- rejection percentage;
- before/after RR-versus-NN examples.

Accordingly, formal NN correction remains a reproducibility gap.

## 3. Time-domain HRV

The report describes the following features:

- Mean RR [ms];
- standard deviation of RR intervals [ms];
- minimum RR [ms];
- maximum RR [ms];
- mean heart rate [bpm];
- RMSSD;
- pRR50.

Mean heart rate was calculated as:

`HR mean = 60000 / Mean RR`

with Mean RR expressed in milliseconds.

The report defines RMSSD, while the final result table and decision-tree figure use the label `RMSS`. This repository retains that discrepancy as documentation rather than silently changing historical result labels.

## 4. Frequency-domain HRV

The report uses an autoregressive (AR) method for power spectral density estimation.

Reported configuration:

- AR order: 16;
- coefficient estimation: Burg-Lattice;
- VLF: 0.003-0.04 Hz;
- LF: 0.04-0.15 Hz;
- HF: 0.15-0.40 Hz.

Reported derived measures include:

- VLF power;
- LF power;
- HF power;
- LF/HF;
- normalized LF;
- normalized HF.

The normalized LF/HF quantities exclude VLF from the denominator, as described in the report.

### Spectral reproducibility gap

The preserved documentation does not specify how the unevenly spaced RR sequence was prepared before AR spectral estimation. In particular, interpolation, resampling frequency, detrending, and stationarity handling are not preserved.

## 5. Experimental-condition classification

The report states that time-domain HRV results were used as a small dataset for a scikit-learn decision tree in Google Colab.

The available report shows a tree based on RMSSD/`RMSS`, minimum RR, and mean RR. The original notebook is missing, and no independent validation protocol is reported.

The output must therefore be interpreted as exploratory classification of the assigned experimental conditions, not clinical diagnosis of stress.
