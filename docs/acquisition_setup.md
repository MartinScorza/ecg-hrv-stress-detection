# ECG acquisition setup

This document records acquisition details supported by the academic report and the recovered project backup. Parameters that remain unavailable are identified explicitly rather than inferred.

## Electrode configuration

The report describes three surface Ag/AgCl electrodes in an Einthoven-type placement:

- positive electrode: left wrist (LA);
- negative electrode: right wrist (RA);
- reference electrode: left ankle.

Skin preparation used alcohol and abrasive gel to reduce contact impedance and improve signal quality.

Participants were seated because an examination table was not available. They were instructed to remain still and avoid speaking during acquisition.

## Analog chain

Reported sequence:

1. differential input preamplifier: **NL 844 AC**;
2. reported preamplifier gain: **1000**;
3. electrical isolator between the participant-side electronics and the rest of the system;
4. high-pass filtering for baseline-drift reduction;
5. second amplification stage with reported gain **5**;
6. low-pass anti-aliasing filter with reported cutoff **150 Hz**;
7. analog-to-digital acquisition through an NI acquisition card.

## Sampling rate - independently verified

The report specifies a sampling frequency of **500 Hz**.

The recovered original condition recordings provide independent confirmation: their time columns progress in regular **0.002 s** increments.

`1 / 0.002 s = 500 Hz`

This makes the 500 Hz acquisition rate a source-file-verified parameter rather than a report-only statement.

## Recording duration

The principal stress/relaxation recordings inspected in the recovered backup span approximately **306 to 381 seconds**. This is compatible with an approximately five-minute experimental condition with some variation or acquisition overhead.

The exact planned duration and stop logic of the selected final VI should still be checked in LabVIEW before documenting a fixed runtime requirement.

## File format observations

Recovered acquisition exports are numeric delimited text/CSV-style files containing the ECG signal and timestamp values.

Several files use two columns. Some later variants contain a third field that appears zero-valued in the inspected recordings. Because historical acquisition versions exist in the backup, a single universal input schema should not be claimed until the final export path is inspected in LabVIEW.

## LabVIEW project evidence

A recovered legacy file named `ACAUISITION.lvproj` references `AQUIISITON.vi` and `Global 1.vi`. It reports `LVVersion="23008000"`.

The project file does **not** reference the selected final `PARALLEL FINAL.vi` / `Processing_data_subvi_V23.vi` pair, so it is treated as evidence of an earlier acquisition setup rather than the final runnable project definition.

## Runtime configuration still unresolved

The recovered material still does not establish the following parameters with enough confidence for a clean hardware reproduction:

- exact NI acquisition-card model;
- exact device and channel name used with the selected final VI;
- terminal configuration;
- analog input range;
- high-pass filter cutoff/order;
- isolator model;
- DAQ buffering parameters;
- synchronization settings;
- exact LabVIEW version used to save the selected final VI pair.

These items should be documented from the original laboratory setup or by opening the preserved VIs in a compatible LabVIEW environment before claiming end-to-end hardware reproducibility.
