# BIDS Conversion — Neuroventure

## Tool

**HeuDiConv** was used to convert raw DICOM data into BIDS-compliant NIfTI format.

## Heuristics File

A custom heuristics `.py` file was written to map Neuroventure DICOM series descriptions to BIDS naming conventions.

<!-- TODO: Embed or link to the heuristics .py file -->

## BIDS Naming Convention

| BIDS Name | Original Sequence |
|-----------|------------------|
| `sub-XXX/ses-XX/anat/..._T1w` | T1 SAG MPRAGE grappa2 |
| `sub-XXX/ses-XX/func/..._task-rest_bold` | BOLD MOSAIC 64_REST |
| `sub-XXX/ses-XX/func/..._task-MIDT_bold` | BOLD MOSAIC 64_MIDT |
| `sub-XXX/ses-XX/func/..._task-STOP_bold` | BOLD MOSAIC 64_STOP |
| `sub-XXX/ses-XX/dwi/..._dwi` | DTI AX EP2D grappa2 2mm |
| `sub-XXX/ses-XX/fmap/...` | gre_field_mapping for DTI |

## BIDS Validation

BIDS Validator was run on the full dataset after conversion.

<!-- TODO: Attach BIDS validator output .txt file -->

## Steps to Single-Acquisition BIDS Dataset

Several issues were encountered and resolved to achieve a clean single-acquisition, single-session, single-subject BIDS dataset:

<!-- TODO: Document the specific steps taken -->

## Files to Add

- [ ] Heuristics `.py` file
- [ ] BIDS validator output (`.txt`)
- [ ] HeuDiConv command used (with all flags)
