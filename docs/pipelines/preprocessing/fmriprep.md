# fMRIPrep

## Overview

[fMRIPrep](https://fmriprep.org/) is a robust preprocessing pipeline for functional MRI data. It uses a combination of tools from FSL, ANTs, FreeSurfer, and AFNI, selecting the best software implementation for each preprocessing stage.

## What fMRIPrep Does

### Anatomical Preprocessing

1. **Intensity Correction** — N4BiasFieldCorrection for non-uniformity correction
2. **Skull-Stripping** — antsBrainExtraction.sh with OASIS30ANTs template
3. **Tissue Segmentation** — FSL FAST for CSF, WM, and GM segmentation
4. **Surface Reconstruction** — FreeSurfer recon-all
5. **Brain Mask Refinement** — Mindboggle method
6. **Spatial Normalization** — antsRegistration to MNI152NLin2009cAsym

### Functional Preprocessing

1. **Head-Motion Correction** — mcflirt (FSL)
2. **Slice-Time Correction** — 3dTshift (AFNI)
3. **Native Space Resampling** — using estimated motion parameters
4. **Co-Registration** — bbregister (FreeSurfer) BOLD-to-T1w
5. **Confound Estimation** — FD, DVARS, global signals, CompCor (tCompCor, aCompCor)
6. **Outlier Detection** — based on FD and DVARS thresholds
7. **Standard Space Resampling** — antsApplyTransforms to MNI space

## Basic Command

```bash
fmriprep /path/to/bids_root/ /path/to/output/ participant \
  -w /path/to/work/
```

## Key Arguments

See the [fMRIPrep Arguments](../../neuroventure-detailed/fmriprep/arguments.md) page for a detailed breakdown of all arguments.

## Interpreting Outputs

See the [fMRIPrep Outputs](../../neuroventure-detailed/fmriprep/outputs.md) page for a guide to output files.

!!! tip "Methods Section"
    Each fMRIPrep run generates an HTML summary with a methods boilerplate and citations for all sub-tools used (FSL, AFNI, FreeSurfer, etc.). Use this directly in your papers.
