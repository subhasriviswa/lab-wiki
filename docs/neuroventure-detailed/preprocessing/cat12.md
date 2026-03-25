# CAT12 QC — Neuroventure

## Overview

CAT12 (version 12.8.2) was used as the first quality control step for structural T1-weighted images in the Neuroventure dataset. A longitudinal pipeline was used with the **neurodevelopmental** registration parameter.

## Purpose

- Generate Image Quality Rating (IQR) reports for all participants
- Check for abnormalities at surface and volume levels
- Identify problematic scans before fMRIPrep processing

## QC Parameters

| Metric | Cutoff | Reference |
|--------|--------|-----------|
| IQR | *Add threshold* | *Add citation* |
| Noise ratio | *Add threshold* | *Add citation* |

## Handling Multiple T1 Scans

More than one T1 image was found for some subjects within a single session.

<!-- TODO: Document the protocol for selecting which T1 to use -->

## Running CAT12

<!-- TODO: Add the MATLAB/SPM batch script used -->
<!-- TODO: Add screenshots of the CAT12 interface settings -->

## Files to Add

- [ ] CAT12 batch script
- [ ] QC threshold values and literature references
- [ ] Protocol for handling multiple T1 scans
- [ ] Example IQR report screenshot
