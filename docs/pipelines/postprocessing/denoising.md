# Denoising Strategies

## Overview

fMRIPrep performs preprocessing but does **not** apply denoising (confound regression). Denoising must be done as a separate postprocessing step.

!!! warning "Important"
    The choice of denoising strategy impacts functional connectivity results and case-control differences. Choose carefully based on your analysis goals.

## Key Concepts

- **Aggressive denoising**: Design matrix includes only confound variables; residuals are used for further analysis
- **Non-aggressive denoising**: Design matrix includes confound variables AND variables of interest

## Recommended Strategies

Based on benchmarking literature (Ciric et al., 2017; Powers et al., 2012, 2018; Wang, 2023):

| Strategy | Best For | Notes |
|----------|----------|-------|
| `simple + GSR` | Low-motion datasets | Preserves continuous temporal sampling |
| `scrubbing (0.5mm)` | High-motion datasets | Best denoising quality; costs temporal degrees of freedom |
| `ICA-AROMA` | Varies | Requires `--use-aroma` flag during fMRIPrep (deprecated in v24+) |
| `CompCor` | General use | Component-based noise correction |

## Tools

- **Nilearn** — `load_confounds_strategy()` API with built-in strategies. See [Nilearn Strategies](../../neuroventure-detailed/denoising/nilearn.md)
- **CONN Toolbox** — GUI-based denoising with additional analysis. See [CONN Toolbox](../../neuroventure-detailed/denoising/conn.md)

## Key References

- Esteban et al. (2020). Analysis of task-based fMRI data preprocessed with fMRIPrep. *Nature Protocols*.
- Ciric et al. (2017). Benchmarking of participant-level confound regression strategies. *NeuroImage*.
- Powers et al. (2012, 2018). Denoising strategies for resting-state fMRI.
- Wang, H-T. (2023). Continuous evaluation of denoising strategies in resting-state fMRI connectivity using fMRIPrep and Nilearn. *Preprint*.
