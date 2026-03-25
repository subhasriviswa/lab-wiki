# Denoising Overview — Neuroventure

## What Happens After fMRIPrep

fMRIPrep preprocesses the data but does **not** denoise it. The preprocessed BOLD data still contains confounds (motion artifacts, physiological noise) that must be regressed out before connectivity or activation analysis.

## Error Checking First

Before denoising, check the fMRIPrep HTML reports:

- Out of 141 preprocessed subjects, **19 had errors**
- Most errors occurred at the **bbregister step**
- Use the BeautifulSoup parsing script to identify which subjects had errors
- Investigate the `desc` files for error details

<!-- TODO: Add the error CSV and the parsing script -->

## Denoising Concepts

### Aggressive vs Non-Aggressive

| Type | Design Matrix | Use Case |
|------|--------------|----------|
| **Aggressive** | Confounds only (use residuals) | Resting-state connectivity |
| **Non-aggressive** | Confounds + variables of interest | Task-based fMRI |

## Literature Review

### Esteban et al. (2020) — Nature Protocols

- Protocol for task-based fMRI analysis with fMRIPrep
- Does **not** cover further denoising beyond fMRIPrep
- This is noted as a limitation

### Ciric et al. (2017) & Powers et al. (2012, 2018)

Examined 19 denoising pipelines across 4 datasets:

- **No single method offers perfect motion control**
- **Censoring and ICA-AROMA** perform well across most benchmarks
- **Pipeline choice impacts case-control differences** in functional connectivity
- Note: these datasets were not preprocessed with fMRIPrep

### Wang (2023) — Preprint

Benchmarked denoising strategies specifically for fMRIPrep + Nilearn:

**Four strategies evaluated:**

1. `simple` — basic motion + WM/CSF regression
2. `scrubbing` — censoring high-motion volumes
3. `compcor` — component-based noise regression
4. `ica_aroma` — ICA-based artifact removal

**Four QC metrics used:**

1. **Loss of degrees of freedom** — regressors + censored volumes
2. **QC-FC** (Power et al., 2015) — partial correlation between motion and connectivity
3. **DM-FC** (Power et al., 2012) — distance-dependent motion effects
4. **Network modularity** (Satterthwaite et al., 2012) — Louvain community detection (BCT)

**Recommendations:**

| Scenario | Recommended Strategy |
|----------|---------------------|
| Low-motion data, preserve temporal continuity | `simple + GSR` |
| High-motion data, quality over temporal DOF | `scrubbing (0.5mm)` |

!!! warning
    ICA-AROMA performance departed from previous benchmarks and only performed well in one metric. Additionally, denoising strategy performance can vary across fMRIPrep versions.
