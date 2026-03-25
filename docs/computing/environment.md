# Environment Setup

## Python Environment

### Setting Up a Virtual Environment on HPC

```bash
module load python/3.x
python -m venv ~/envs/neuroimaging
source ~/envs/neuroimaging/bin/activate
pip install nilearn nibabel pandas numpy scipy matplotlib seaborn
```

### Key Python Packages

| Package | Use |
|---------|-----|
| nilearn | fMRI analysis, denoising, connectivity |
| nibabel | Reading/writing neuroimaging files |
| pybids | Querying BIDS datasets |
| pandas | Data manipulation |
| matplotlib / seaborn | Visualization |
| beautifulsoup4 | Parsing fMRIPrep HTML reports |

## Singularity/Apptainer Containers

Neuroimaging tools are often run via containers on HPC:

```bash
module load apptainer  # or singularity

# Pull a container
apptainer pull fmriprep.sif docker://nipreps/fmriprep:<version>
apptainer pull mriqc.sif docker://nipreps/mriqc:<version>
```

## MATLAB

<!-- TODO: Add MATLAB module loading and CONN/SPM/CAT12 setup on HPC -->

## FreeSurfer

```bash
module load freesurfer
export FREESURFER_HOME=/path/to/freesurfer
source $FREESURFER_HOME/SetUpFreeSurfer.sh
```

!!! note
    You need a FreeSurfer license file. Get one free at [FreeSurfer registration](https://surfer.nmr.mgh.harvard.edu/registration.html).

## FSL

```bash
module load fsl
source $FSLDIR/etc/fslconf/fsl.sh
```
