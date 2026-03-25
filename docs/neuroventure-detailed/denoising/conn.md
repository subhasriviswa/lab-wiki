# CONN Toolbox

## Overview

[CONN](https://web.conn-toolbox.org/) is a MATLAB-based toolbox for functional connectivity analysis. It can import fMRIPrep-preprocessed BIDS datasets and perform denoising and connectivity analysis through a GUI.

## Importing fMRIPrep Outputs

CONN can import a full BIDS dataset with fMRIPrep derivatives:

1. Open CONN in MATLAB
2. Use the BIDS import option
3. CONN automatically recognizes:
    - Confound regressors
    - WM and GM masks
    - All necessary derivatives

!!! success "Tested"
    A full participant (all sessions, longitudinal) was successfully imported into CONN using the BIDS import feature.

## Denoising in CONN

CONN has a built-in denoising pipeline. After import:

1. Run the **Setup** tab
2. Configure the **Denoising** tab
3. Additional parameters can be added (ICA, GSR) on top of the existing pipeline

See [CONN denoising documentation](https://web.conn-toolbox.org/fmri-methods/denoising-pipeline) for details on the default pipeline.

## Analysis Pipeline

After denoising, CONN supports:

- **1st level analysis**: Individual subject connectivity
- **2nd level analysis**: Group-level statistics
- Custom atlas upload
- Brain Connectivity Toolbox (BCT) integration for graph measures

## Running CONN on Compute Canada

<!-- TODO: Document how to run CONN on HPC (headless MATLAB, job scripts) -->

## Pros and Cons

| Pros | Cons |
|------|------|
| Minimal coding required | Cannot fully customize denoising |
| GUI-based, visual workflow | MATLAB license required |
| Built-in 1st and 2nd level analysis | HPC setup needs configuration |
| BCT integration for graph measures | |
| Custom atlas support | |
