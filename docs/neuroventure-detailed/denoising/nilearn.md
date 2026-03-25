# Nilearn Denoising Strategies

## Overview

[Nilearn](https://nilearn.github.io/) provides a Python API for loading and applying denoising strategies to fMRIPrep outputs. The `load_confounds_strategy()` function allows you to select from predefined strategies.

## Installation

```bash
pip install nilearn
```

## Basic Usage

```python
from nilearn.interfaces.fmriprep import load_confounds_strategy

# Load confounds with a predefined strategy
confounds, sample_mask = load_confounds_strategy(
    img_files='path/to/sub-XXX_task-rest_space-MNI152NLin2009cAsym_desc-preproc_bold.nii.gz',
    denoise_strategy='simple',  # or 'scrubbing', 'compcor', 'ica_aroma'
    motion='full',
    global_signal='basic'  # adds GSR
)
```

## Available Strategies

### simple

Basic confound regression with motion parameters, WM, and CSF signals.

```python
confounds, sample_mask = load_confounds_strategy(
    img_files=bold_file,
    denoise_strategy='simple',
    global_signal='basic'  # recommended for low-motion data
)
```

### scrubbing

Censors high-motion volumes based on framewise displacement.

```python
confounds, sample_mask = load_confounds_strategy(
    img_files=bold_file,
    denoise_strategy='scrubbing',
    fd_threshold=0.5,  # recommended threshold
    global_signal='basic'
)
```

### compcor

Component-based noise correction using CompCor regressors.

```python
confounds, sample_mask = load_confounds_strategy(
    img_files=bold_file,
    denoise_strategy='compcor'
)
```

### ica_aroma

!!! warning
    Only available if fMRIPrep was run with `--use-aroma` flag. This flag is **deprecated** in fMRIPrep v24+.

```python
confounds, sample_mask = load_confounds_strategy(
    img_files=bold_file,
    denoise_strategy='ica_aroma'
)
```

## Full Example: Extract Denoised Time Series

```python
from nilearn.interfaces.fmriprep import load_confounds_strategy
from nilearn.maskers import NiftiLabelsMasker

# Load confounds
bold_file = 'path/to/sub-XXX_task-rest_space-MNI152NLin2009cAsym_desc-preproc_bold.nii.gz'
confounds, sample_mask = load_confounds_strategy(
    img_files=bold_file,
    denoise_strategy='simple',
    global_signal='basic'
)

# Extract time series with denoising
masker = NiftiLabelsMasker(
    labels_img='path/to/atlas.nii.gz',
    standardize=True
)
time_series = masker.fit_transform(
    bold_file,
    confounds=confounds,
    sample_mask=sample_mask
)
```

## Batch Processing

<!-- TODO: Add the batch processing script for all subjects -->

## Pros and Cons

| Pros | Cons |
|------|------|
| Integrated with Nilearn ecosystem | Requires Python coding |
| Easy batch processing | |
| Flexible strategy selection | |
| Well-documented API | |
