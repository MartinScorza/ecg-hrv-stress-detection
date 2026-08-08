# ECG acquisition setup

This document records acquisition details supported by the original project report. Parameters that are not preserved are explicitly identified rather than inferred.

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

## Sampling

The report specifies a digital sampling frequency of:

**500 Hz**

## Runtime configuration not preserved

The available archive does not establish the following parameters with enough evidence for a reproducible hardware setup:

- NI acquisition-card model;
- exact device and channel name;
- terminal configuration;
- analog input range;
- high-pass filter cutoff/order;
- isolator model;
- acquisition duration;
- number of samples per read;
- DAQ buffering parameters;
- synchronization settings;
- exact LabVIEW version.

These items should be recovered from the original laboratory setup or an original LabVIEW project configuration before claiming end-to-end hardware reproducibility.
