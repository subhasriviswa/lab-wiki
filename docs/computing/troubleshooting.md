# Troubleshooting

## Common HPC Issues

### Job killed — out of memory

Increase memory allocation:

```bash
#SBATCH --mem=64G
```

Or use `--mem-per-cpu` for parallel jobs.

### Job timeout

Increase wall time or split into smaller jobs:

```bash
#SBATCH --time=48:00:00
```

### Singularity: Permission denied

Ensure bind paths are correct:

```bash
singularity run --cleanenv -B /scratch:/scratch container.sif
```

### Module not found

Check available modules:

```bash
module spider <software_name>
module avail 2>&1 | grep <software_name>
```

## fMRIPrep Issues

### bbregister Failure

The most common fMRIPrep error in the Neuroventure dataset. Possible causes:

- Poor T1w quality
- Excessive motion in BOLD reference
- Field-of-view mismatch between BOLD and T1w

**Workarounds:**

- Try `--bold2t1w-init header` instead of `register`
- Try `--force-no-bbr` to fall back to FLIRT
- Check the T1w with CAT12 QC first

### Out of memory

fMRIPrep is memory-intensive. Recommended minimums:

- **Without FreeSurfer**: 16 GB
- **With FreeSurfer**: 32 GB
- **Longitudinal mode**: 32-64 GB

### Disk space in work directory

fMRIPrep work directories can grow large. Clean up after successful runs:

```bash
# Only after confirming outputs are correct
rm -rf /path/to/work/fmriprep_wf/
```

## BIDS Issues

### BIDS Validator errors after HeuDiConv

Common fixes:

- Missing `.json` sidecars → check `dcm2niix` version
- Task events `.tsv` files missing → create them manually
- Incorrect folder naming → check heuristics file

<!-- TODO: Add more troubleshooting entries as they come up -->
