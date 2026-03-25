# Neuroventure

## Overview

| Field | Details |
|-------|---------|
| **Cohort Name** | Neuroventure |
| **Description** | Longitudinal neuroimaging cohort |
| **N Subjects** | *TBD* |
| **Timepoints** | 3 sessions (ses-01, ses-02, ses-03) |
| **Modalities** | T1 (SAG MPRAGE), fMRI (resting-state, MIDT task, STOP signal task), DTI |
| **Scanner** | *TBD* (note: scanner change at timepoint 3) |
| **BIDS Formatted** | Yes |
| **Data Location** | Compute Canada Cedar cluster — *add path* |
| **PI / Contact** | *TBD* |

## Imaging Sequences

- AAH_Scout_32ch (head-coil)
- SAG TRUFISP
- T1 SAG MPRAGE grappa2
- BOLD MOSAIC 64_MIDT
- BOLD MOSAIC 64_STOP
- BOLD MOSAIC 64_REST
- gre_field_mapping for DTI
- DTI AX EP2D grappa2 2mm 22dir 1000
- DTI AX EP2D grappa2 2mm 23dir 1000
- DTI AX EP2D grappa2 2mm 24dir 1000

!!! warning "Scanner Change at Timepoint 3"
    There was a change of scanner at timepoint 3. Refer to the protocol document for details on TR, TE, slices, and other parameters.

<!-- TODO: Add link to imaging protocol document -->
<!-- TODO: Add graph of expected DICOM file counts per acquisition -->

## Ethical Clearance

| Field | Details |
|-------|---------|
| **Ethics Board** | *TBD* |
| **Protocol Number** | *TBD* |
| **Contact to be added to project** | *TBD* |

## Data Dictionary

<!-- TODO: Add link to data dictionary or embed it here -->

## Publications

<!-- TODO: List publications using this dataset -->

## Related Pages

- [BIDS Conversion Details](../../neuroventure-detailed/data/bids-conversion.md)
- [Preprocessing Pipeline](../../neuroventure-detailed/index.md)
- [Data Anomalies](../../neuroventure-detailed/data/anomalies.md)
