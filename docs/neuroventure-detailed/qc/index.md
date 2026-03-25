# Quality Control — Neuroventure

## QC Pipeline Overview

Quality control is performed at multiple stages of the pipeline:

| Stage | Tool | What to Check |
|-------|------|---------------|
| **Raw data** | Manual / scan notes | Scan completion, participant notes |
| **BIDS conversion** | BIDS Validator | Naming, missing files, JSON sidecars |
| **Structural T1** | CAT12 | IQR, noise ratio, surface/volume quality |
| **fMRIPrep** | HTML reports | Registration quality, errors, motion |
| **Post-denoising** | QC-FC metrics | Motion-connectivity correlations |

## Data-Level QC

- [ ] Scan completion file (xlsx) — verify all expected scans exist
- [ ] QC during scan notes (xlsx) — flag participants with issues
- [ ] BIDS validator output — resolve all errors, document warnings

## CAT12 Structural QC

See [CAT12 QC](../preprocessing/cat12.md) for details.

## fMRIPrep QC

### HTML Report Review

Each subject gets an HTML report. Key things to check:

1. **Brain mask quality** — does the mask cover the whole brain?
2. **Registration** — is BOLD-to-T1w alignment good?
3. **Normalization** — does MNI alignment look correct?
4. **Motion plots** — excessive motion?
5. **Errors section** — any processing failures?

### Automated Error Checking

Use BeautifulSoup to parse all HTML reports:

<!-- TODO: Add the full parsing script -->

### Motion-Based Exclusion

| Metric | Threshold | Action |
|--------|-----------|--------|
| Mean FD | *Add value* | Exclude subject |
| % volumes > FD threshold | *Add value* | Exclude or scrub |

## Post-Denoising QC

After denoising, evaluate using:

1. **QC-FC** — correlation between motion and connectivity should be near zero
2. **DM-FC** — distance-dependent effects should be minimized
3. **Network modularity** — should be within expected range

## Files to Add

- [ ] Scan completion xlsx
- [ ] QC during scan xlsx
- [ ] BIDS validator output
- [ ] CAT12 IQR summary
- [ ] fMRIPrep error CSV
- [ ] Motion exclusion criteria documentation
