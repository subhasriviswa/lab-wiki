# Neuroventure Pipeline (Detailed)

This section contains in-depth documentation of the complete preprocessing and postprocessing pipeline built for the Neuroventure dataset, covering resting-state fMRI, task fMRI (MIDT, STOP), and DTI.

**Last Update**: 2024-01-11

**Major Contributors**: Sean Spiney, Maria Didaskalou, Jeremy Watts, and Subhasri Viswanathan

## Pipeline Flow

```
Raw DICOM Data
    │
    ▼
BIDS Conversion (HeuDiConv)
    │
    ▼
BIDS Validation
    │
    ▼
Anomaly Documentation
    │
    ▼
CAT12 Structural QC
    │
    ▼
fMRIPrep (Preprocessing)
    │
    ▼
fMRIPrep QC (HTML Reports)
    │
    ▼
Denoising (Nilearn / CONN)
    │
    ▼
Connectivity Analysis
```

## Sections

| Section | Description |
|---------|-------------|
| [Data Overview](data/overview.md) | Imaging sequences, scanner details, data organization |
| [BIDS Conversion](data/bids-conversion.md) | HeuDiConv setup, heuristics file, BIDS validation |
| [Data Anomalies](data/anomalies.md) | Known issues, unusual headers, missing scans |
| [CAT12 QC](preprocessing/cat12.md) | Structural T1 quality control details |
| [fMRIPrep Setup](fmriprep/setup.md) | Installation and execution on HPC |
| [fMRIPrep Arguments](fmriprep/arguments.md) | All arguments used with explanations |
| [fMRIPrep Outputs](fmriprep/outputs.md) | Output file structure and descriptions |
| [Denoising Overview](denoising/overview.md) | Post-fMRIPrep denoising concepts and literature |
| [Nilearn Strategies](denoising/nilearn.md) | Using Nilearn's denoising API |
| [CONN Toolbox](denoising/conn.md) | Using CONN for denoising and analysis |
| [Quality Control](qc/index.md) | QC procedures across the pipeline |
