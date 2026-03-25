# CAT12 Quality Control

## Overview

[CAT12](https://neuro-jena.github.io/cat/) (Computational Anatomy Toolbox) is used as the first level of quality control for structural T1-weighted images. It generates Image Quality Rating (IQR) reports to check for abnormalities at the surface and volume levels.

## Version

CAT12 version 12.8.2 (runs within SPM/MATLAB)

## Key QC Metrics

- **IQR (Image Quality Rating)**: Overall image quality score
- **Noise ratio**: Signal-to-noise assessment

!!! info "QC Thresholds"
    Based on the literature, the following cutoff values are used:
    <!-- TODO: Add specific IQR and noise ratio cutoff values and literature references -->

## Longitudinal Pipeline

For longitudinal datasets, use CAT12's longitudinal pipeline with the **neurodevelopmental** registration parameter selected.

## Running CAT12

<!-- TODO: Add MATLAB/SPM batch script or command for running CAT12 -->

## Handling Multiple T1 Scans

When more than one T1 image exists for a single session, refer to the CAT12 quality control document for the protocol on how these were handled.

<!-- TODO: Add the protocol for handling multiple T1 scans -->

## Output

CAT12 generates:

- Individual IQR reports per subject/session
- Surface and volume quality assessments
- PDF reports with visual QC information
