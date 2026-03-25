# Pipelines Overview

This section documents general neuroimaging analysis pipelines used across cohorts. For the full detailed walkthrough specific to the Neuroventure dataset, see the [Neuroventure Pipeline (Detailed)](../neuroventure-detailed/index.md) section.

## Preprocessing

| Step | Tool | Description |
|------|------|-------------|
| [DICOM to BIDS](preprocessing/dicom-to-bids.md) | HeuDiConv | Converting raw DICOM data to BIDS format |
| [CAT12 QC](preprocessing/cat12-qc.md) | CAT12 | Structural T1 quality control using IQR reports |
| [fMRIPrep](preprocessing/fmriprep.md) | fMRIPrep | Anatomical and functional MRI preprocessing |

## Postprocessing

| Step | Tool | Description |
|------|------|-------------|
| [Denoising](postprocessing/denoising.md) | Nilearn / CONN | Post-fMRIPrep confound regression strategies |
| [Connectivity Analysis](postprocessing/connectivity.md) | Various | Functional connectivity and graph analysis |
