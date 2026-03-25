# Neuroventure Data Overview

## Dataset Summary

The Neuroventure cohort is a longitudinal neuroimaging dataset with 3 sessions (timepoints).

## Imaging Sequences

| Sequence | Description |
|----------|-------------|
| AAH_Scout_32ch | Head-coil scout |
| SAG TRUFISP | Sagittal TRUFISP |
| T1 SAG MPRAGE grappa2 | Structural T1-weighted |
| BOLD MOSAIC 64_MIDT | Task fMRI — Monetary Incentive Delay Task |
| BOLD MOSAIC 64_STOP | Task fMRI — STOP Signal Task |
| BOLD MOSAIC 64_REST | Resting-state fMRI |
| gre_field_mapping for DTI | Field map for diffusion |
| DTI AX EP2D grappa2 2mm 22dir 1000 | Diffusion — 22 directions |
| DTI AX EP2D grappa2 2mm 23dir 1000 | Diffusion — 23 directions |
| DTI AX EP2D grappa2 2mm 24dir 1000 | Diffusion — 24 directions |

!!! warning "Scanner Change at Timepoint 3"
    The scanner was changed at timepoint 3. This affects TR, TE, and other acquisition parameters. See the imaging protocol document for details.

<!-- TODO: Add link to protocol document with TR, TE, slices parameters -->
<!-- TODO: Add graph showing expected DICOM file counts per acquisition type -->

## Data Organization

The BIDS-validated dataset is stored on Compute Canada.

| Item | Location |
|------|----------|
| **BIDS dataset** | *Add Cedar cluster path* |
| **Raw DICOMs** | *Add path* |
| **fMRIPrep outputs** | *Add path* |

## Scan File Mapping

<!-- TODO: Add details on the scan file mapping used to reach single-acquisition, single-session, single-subject BIDS structure -->

## Files to Add

- [ ] Imaging protocol document (TR, TE, slices for each sequence)
- [ ] Expected DICOM file count graph
- [ ] Scan completion dates (xlsx)
- [ ] QC during scan notes (xlsx)
