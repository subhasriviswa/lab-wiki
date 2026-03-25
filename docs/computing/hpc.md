# HPC Resources

## Compute Canada

The lab uses the following Compute Canada clusters:

### Fir

| Field | Details |
|-------|---------|
| **Cluster** | Fir |
| **URL** | *Add login URL* |
| **Access** | Compute Canada account required |
| **Storage** | *Add project/scratch paths* |
| **Job Scheduler** | SLURM |

### NIBI

| Field | Details |
|-------|---------|
| **Cluster** | NIBI |
| **URL** | *Add login URL* |
| **Access** | *Add access instructions* |
| **Storage** | *Add project/scratch paths* |
| **Job Scheduler** | *Add details* |

## Getting Access

1. Create a Compute Canada account at [CCDB](https://ccdb.alliancecan.ca/)
2. Request to be added to the lab's allocation (PI sponsor)
3. Contact: *Add PI or admin contact*

## Key Paths

| Data | Cluster | Path |
|------|---------|------|
| Neuroventure BIDS | *TBD* | *Add path* |
| fMRIPrep outputs | *TBD* | *Add path* |
| Shared scripts | *TBD* | *Add path* |
| Software containers | *TBD* | *Add path* |

## SLURM Basics

### Submit a job

```bash
sbatch job_script.sh
```

### Check job status

```bash
squeue -u $USER
```

### Cancel a job

```bash
scancel <job_id>
```

### Example Job Script

```bash
#!/bin/bash
#SBATCH --job-name=my_job
#SBATCH --time=12:00:00
#SBATCH --cpus-per-task=4
#SBATCH --mem=16G
#SBATCH --output=%x_%j.out
#SBATCH --error=%x_%j.err

module load <software>
# your commands here
```

## Storage Policies

<!-- TODO: Add details on scratch purge policies, project quotas, etc. -->
