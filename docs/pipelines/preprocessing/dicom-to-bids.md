# DICOM to BIDS Conversion

## Overview

Raw DICOM data from the scanner needs to be converted into [BIDS format](https://bids.neuroimaging.io/) for standardized processing with modern neuroimaging tools.

## Tools

### HeuDiConv

[HeuDiConv](https://heudiconv.readthedocs.io/) is used to convert DICOM files to NIfTI in BIDS-compliant directory structure.

#### Installation

```bash
pip install heudiconv
```

#### Basic Usage

```bash
heudiconv -d /path/to/dicoms/{subject}/{session}/*.dcm \
  -o /path/to/bids_output/ \
  -f /path/to/heuristics.py \
  -s <subject_id> \
  -ss <session_id> \
  -c dcm2niix \
  -b --overwrite
```

#### Heuristics File

The heuristics file defines how DICOM series are mapped to BIDS naming conventions. Each cohort may need its own heuristics file.

<!-- TODO: Add example heuristics file or link to one -->

```python
# Example heuristics structure
import os

def create_key(template, outtype=('nii.gz',), annotation_classes=None):
    if template is None or not template:
        raise ValueError('Template must be a valid format string')
    return template, outtype, annotation_classes

def infotodict(seqinfo):
    """Heuristic evaluator for determining which runs belong where."""
    # Define your keys
    t1w = create_key('sub-{subject}/{session}/anat/sub-{subject}_{session}_T1w')
    rest = create_key('sub-{subject}/{session}/func/sub-{subject}_{session}_task-rest_bold')
    # ... add more keys

    info = {t1w: [], rest: []}

    for s in seqinfo:
        # Match series descriptions to keys
        if 'MPRAGE' in s.series_description:
            info[t1w].append(s.series_id)
        elif 'REST' in s.series_description:
            info[rest].append(s.series_id)

    return info
```

### BIDS Validator

After conversion, always validate your dataset:

```bash
bids-validator /path/to/bids_dataset/
```

!!! tip
    Review all warnings and errors from the BIDS validator. Save the output to a text file for documentation.
