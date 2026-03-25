# fMRIPrep Outputs — Neuroventure

## Directory Structure

fMRIPrep outputs mirror the BIDS input structure:

```
output/
├── sub-014/
│   ├── anat/
│   ├── figures/
│   ├── log/
│   ├── ses-01/
│   │   └── func/
│   ├── ses-02/
│   │   └── func/
│   └── ses-03/
│       └── func/
├── sub-015/
│   └── ...
└── sourcedata/
    └── freesurfer/
```

## Anatomical Outputs

For each T1-weighted image:

| File | Description |
|------|-------------|
| `sub-XXX_space-<space>_desc-preproc_T1w.nii.gz` | Preprocessed T1w image |
| `sub-XXX_space-<space>_desc-brain_mask.nii.gz` | Brain mask |
| `sub-XXX_space-<space>_dseg.nii.gz` | Discrete segmentation |
| `sub-XXX_space-<space>_label-CSF_probseg.nii.gz` | CSF probability map |
| `sub-XXX_space-<space>_label-GM_probseg.nii.gz` | Gray matter probability map |
| `sub-XXX_space-<space>_label-WM_probseg.nii.gz` | White matter probability map |

### BIDS Entities Explained

- **`desc`** (description): Distinguishes between different processing versions of the same input
- **`dseg`** (discrete segmentation): Integer-labeled segmentation map
- **`probseg`** (probabilistic segmentation): Probability maps for each tissue class

## Functional Outputs

<!-- TODO: List the functional output files per session -->

## Confounds File

Each functional run produces a `_desc-confounds_timeseries.tsv` containing:

- Framewise displacement (FD)
- DVARS
- Global signals (CSF, WM, global)
- CompCor components (aCompCor, tCompCor)
- Motion parameters (6 rigid-body)
- Outlier flags

## HTML Reports

Each subject gets a visual QC report (`sub-XXX.html`) showing:

- Each preprocessing step
- Registration quality
- Errors encountered

!!! tip "Parsing HTML Reports"
    Use BeautifulSoup to batch-parse all HTML reports and extract error summaries:

    ```python
    from bs4 import BeautifulSoup
    import glob

    for html_file in glob.glob('output/sub-*.html'):
        with open(html_file) as f:
            soup = BeautifulSoup(f, 'html.parser')
            # Check for errors section
            errors = soup.find_all(string=lambda t: 'error' in t.lower() if t else False)
            if errors:
                print(f"{html_file}: {len(errors)} error mentions")
    ```

!!! tip "Methods Boilerplate"
    The HTML report includes a ready-to-use methods section with proper citations for all sub-tools (FSL, AFNI, FreeSurfer, ANTs). Copy this directly into your paper's methods.
