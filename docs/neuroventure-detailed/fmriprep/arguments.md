# fMRIPrep Arguments — Neuroventure

## Command Used

<!-- TODO: Add the exact fMRIPrep command with all flags used for Neuroventure -->

```bash
# Add the actual command here
fmriprep /path/to/bids /path/to/output participant \
  -w /path/to/work \
  # ... all flags used
```

## Positional Arguments

| Argument | Description |
|----------|-------------|
| `bids_dir` | Root folder of BIDS dataset (sub-XXXXX folders at top level) |
| `output_dir` | Output path for preprocessed data and reports |
| `analysis_level` | Always `participant` for fMRIPrep |

## BIDS Filtering

| Flag | Description |
|------|-------------|
| `--skip-bids-validation` | Skip BIDS validation (use if already validated) |
| `--participant-label` | Process specific subjects |
| `-t, --task-id` | Process specific task only |
| `--bids-filter-file` | JSON file for custom BIDS input filters |
| `--anat-derivatives` | Reuse anatomical derivatives (not recommended) |

## Performance

| Flag | Description |
|------|-------------|
| `--nprocs` | Max threads across all processes |
| `--omp-nthreads` | Max threads per process |
| `--mem` | Memory upper bound (MB) |
| `--low-mem` | Reduce memory usage (increases disk usage) |

## Workflow Configuration

| Flag | Description | Our Setting |
|------|-------------|-------------|
| `--output-spaces` | Target spaces for resampling | *Add value* |
| `--longitudinal` | Longitudinal dataset handling | Yes |
| `--bold2t1w-init` | BOLD-to-T1w initialization (`register` or `header`) | *Add value* |
| `--bold2t1w-dof` | Degrees of freedom for BOLD-to-T1w (6, 9, 12) | *Add value* |
| `--slice-time-ref` | Reference slice time (0=start, 0.5=mid, 1=end) | *Add value* |
| `--dummy-scans` | Non-steady-state volumes to remove | *Add value* |

## Output Options

| Flag | Description |
|------|-------------|
| `--output-layout` | `bids` (default) or `legacy` |
| `--cifti-output` | Output as CIFTI (91k or 170k grayordinates) |
| `--medial-surface-nan` | Replace medial wall values with NaN |

## FreeSurfer Options

| Flag | Description |
|------|-------------|
| `--fs-license-file` | Path to FreeSurfer license |
| `--fs-subjects-dir` | Reuse existing FreeSurfer outputs |
| `--fs-no-reconall` | Skip FreeSurfer surface reconstruction |

## Fieldmap Options

| Flag | Description |
|------|-------------|
| `--fmap-bspline` | B-Spline field fitting |
| `--fmap-no-demean` | Do not remove median from fieldmap |
| `--use-syn-sdc` | Fieldmap-less distortion correction |

## Skull Stripping

| Flag | Description |
|------|-------------|
| `--skull-strip-template` | Template for skull stripping (default: OASIS30ANTs) |
| `--skull-strip-t1w` | `auto`, `skip`, or `force` |

## Confound Options

| Flag | Description |
|------|-------------|
| `--fd-spike-threshold` | FD threshold for outlier flagging |
| `--dvars-spike-threshold` | DVARS threshold for outlier flagging |
| `--return-all-components` | Include all CompCor components |

!!! warning "Deprecated: ICA-AROMA"
    `--use-aroma` and related flags are deprecated and will raise errors in fMRIPrep v24+.
