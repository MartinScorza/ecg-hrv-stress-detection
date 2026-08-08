# LabVIEW implementation

This directory preserves the selected final LabVIEW implementation without functional modification.

## Files and relationship

The final project archive supplied for this portfolio contains two complementary VIs:

- `PARALLEL FINAL.vi` - main acquisition/orchestration VI;
- `Processing_data_subvi_V23.vi` - signal-processing subVI.

Binary inspection shows that `PARALLEL FINAL.vi` references `Processing_data_subvi_V23.vi`, while the processing subVI does not reference the main VI. They are therefore different parts of the same workflow, not duplicate versions.

A broader project backup later recovered a third custom dependency:

- `Global 1.vi` - referenced by the main VI and now preserved here from the recovered backup.

The recovered `Global 1.vi` was found in a historical folder of the backup. Its filename and the dependency references are consistent with the missing custom VI previously identified in `PARALLEL FINAL.vi`, but the complete set has not yet been opened and executed in LabVIEW. It is preserved as original project material rather than reconstructed.

## `PARALLEL FINAL.vi`

Verified internal references include:

- `DAQmx Create Channel (AI-Voltage-Basic).vi`
- `DAQmx Timing (Sample Clock).vi`
- `DAQmx Start Task.vi`
- `DAQmx Read (Analog 1D DBL 1Chan NSamp).vi`
- `DAQmx Stop Task.vi`
- `DAQmx Clear Task.vi`
- `Write To Spreadsheet File (DBL).vi`
- `Processing_data_subvi_V23.vi`
- `Global 1.vi`

This supports a role covering analog-input acquisition, timing, task lifecycle, data export and invocation of the processing subVI.

## `Processing_data_subvi_V23.vi`

Verified internal references include:

- `Butterworth Filter.vi`
- `Derivative x(t).vi`
- `TSA Moving Average.vi`
- `Peak Detector.vi`
- `Mean.vi`
- `Std Deviation and Variance.vi`
- `TSA AR Spectrum.vi`
- `Read Delimited Spreadsheet.vi`

The VI also references NI analysis libraries including `NI_AdvSigProcTSA.lvlib`.

## Integrity record

The selected final pair is byte-for-byte identical to the files originally supplied for the portfolio audit.

Git blob identifiers:

- `PARALLEL FINAL.vi`: `4adf9b39acf3373edde3e401173f4ff525684492`
- `Processing_data_subvi_V23.vi`: `3cf479c0688823048d6bf254d51374685f198877`

The recovered global VI is also preserved byte-for-byte from the broader backup:

- `Global 1.vi`: `4ed050e66bd5fd469ed971a8b13f8174dfaa7975`

These identifiers record file integrity; they do not prove successful execution in a clean LabVIEW environment.

## Historical variants intentionally excluded

The broader backup contains several earlier or alternate VIs, including acquisition-only versions, `con while true` variants, and separate Pan-Tompkins processing variants. They are useful for audit history but are not included in the recruiter-facing repository because the originally supplied final archive already identified the selected main VI and processing subVI.

A recovered `.lvproj` also belongs to an earlier acquisition configuration: it references `AQUIISITON.vi` and `Global 1.vi`, not the selected final VI pair. The project file reports `LVVersion="23008000"`, which is evidence about that legacy project environment, not proof of the exact LabVIEW version used to save the final pair.

## Required environment

A clean execution is expected to require at least:

- a compatible LabVIEW installation;
- NI-DAQmx;
- NI signal-processing functionality used by the VIs;
- NI Time Series Analysis / Advanced Signal Processing components;
- compatible NI acquisition hardware.

Still to verify in LabVIEW:

- whether the recovered `Global 1.vi` resolves all custom dependencies of the final main VI;
- exact NI hardware model and device/channel mapping;
- input voltage range and terminal configuration;
- buffer and acquisition controls;
- exact Butterworth filter parameters;
- normalization formula and fixed-threshold scaling;
- moving-window length;
- RR-to-NN artifact-correction logic;
- AR-spectrum preprocessing and settings;
- local export paths.

No functional changes should be made to these VIs until a known-working baseline has been opened and documented in LabVIEW.
