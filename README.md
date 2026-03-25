# Lab Wiki

Internal wiki for the lab's neuroimaging and behavioral datasets, analysis pipelines, and computing resources. Built with [MkDocs](https://www.mkdocs.org/) and the [Material theme](https://squidfunk.github.io/mkdocs-material/).

---

## Quick Start

### Prerequisites

- Python 3.8+
- pip

### Install Dependencies

```bash
pip install mkdocs mkdocs-material
```

### Preview Locally

```bash
mkdocs serve
```

Opens a local server at **http://localhost:8000** with live reload — any file edits show up instantly in the browser.

### Build Static Site

```bash
mkdocs build
```

Generates a static HTML site in the `site/` folder. This can be hosted anywhere (GitHub Pages, a lab server, etc.).

---

## Project Structure

```
lab-wiki/
├── mkdocs.yml                          # Site configuration and navigation
├── docs/
│   ├── index.md                        # Home page
│   ├── datasets/
│   │   ├── index.md                    # Datasets overview
│   │   ├── neuroimaging/
│   │   │   ├── neuroventure.md         # Neuroventure cohort
│   │   │   ├── proventure.md           # Proventure cohort
│   │   │   ├── coventure10.md          # Coventure10 cohort
│   │   │   └── c-pip.md               # C-PIP cohort
│   │   └── behavioral/
│   │       ├── coventure.md            # Coventure cohort
│   │       ├── univenture.md           # Univenture cohort
│   │       ├── cusp.md                 # CUSP cohort
│   │       ├── nutriventure.md         # Nutriventure cohort
│   │       └── opiventure.md           # Opiventure cohort
│   ├── pipelines/
│   │   ├── index.md                    # Pipelines overview
│   │   ├── preprocessing/
│   │   │   ├── dicom-to-bids.md        # HeuDiConv & BIDS conversion
│   │   │   ├── cat12-qc.md            # CAT12 structural QC
│   │   │   └── fmriprep.md            # fMRIPrep overview
│   │   └── postprocessing/
│   │       ├── denoising.md            # Denoising strategies
│   │       └── connectivity.md         # Connectivity analysis
│   ├── neuroventure-detailed/
│   │   ├── index.md                    # Detailed pipeline overview
│   │   ├── data/
│   │   │   ├── overview.md             # Imaging sequences & data org
│   │   │   ├── bids-conversion.md      # BIDS conversion details
│   │   │   └── anomalies.md            # Known data issues
│   │   ├── preprocessing/
│   │   │   └── cat12.md               # CAT12 QC for Neuroventure
│   │   ├── fmriprep/
│   │   │   ├── setup.md               # fMRIPrep HPC setup & SLURM
│   │   │   ├── arguments.md           # All fMRIPrep arguments used
│   │   │   └── outputs.md             # Output file descriptions
│   │   ├── denoising/
│   │   │   ├── overview.md            # Denoising concepts & literature
│   │   │   ├── nilearn.md             # Nilearn denoising API
│   │   │   └── conn.md               # CONN toolbox
│   │   ├── qc/
│   │   │   └── index.md              # QC procedures
│   │   └── assets/images/             # Screenshots for this section
│   ├── computing/
│   │   ├── hpc.md                     # Fir & NIBI cluster info
│   │   ├── environment.md             # Python, Singularity, FSL setup
│   │   └── troubleshooting.md         # Common issues & fixes
│   ├── guides/
│   │   ├── onboarding.md             # New lab member checklist
│   │   └── references.md             # Papers & tool documentation
│   └── assets/images/                 # Shared images and screenshots
├── .gitignore
└── README.md
```

---

## How to Edit

1. All content lives in `docs/` as Markdown files (`.md`)
2. Navigation is defined in `mkdocs.yml` under the `nav:` section
3. To add a new page:
   - Create a `.md` file in the appropriate folder
   - Add it to the `nav:` section in `mkdocs.yml`
4. To add images/screenshots:
   - Drop the file into `docs/assets/images/` (shared) or `docs/neuroventure-detailed/assets/images/` (Neuroventure-specific)
   - Reference in markdown: `![description](assets/images/filename.png)`
5. To add code files (scripts, heuristics files):
   - Either embed directly in a markdown code block (triple backticks with language)
   - Or place the file in the repo and link to it

### Useful Markdown Features

**Code blocks with syntax highlighting:**

````markdown
```python
import nilearn
```

```bash
sbatch job.sh
```
````

**Admonitions (callout boxes):**

```markdown
!!! warning "Title"
    Warning content here.

!!! tip "Title"
    Tip content here.

!!! note
    Note content here.
```

**Task lists:**

```markdown
- [ ] Incomplete task
- [x] Completed task
```

---

## Deployment Options

### Option 1: Local Only

Just run `mkdocs serve` on your machine. Good for personal use.

### Option 2: GitHub Pages (Private Repo)

```bash
mkdocs gh-deploy
```

This pushes the built site to a `gh-pages` branch. With a private repo, only collaborators can access it.

### Option 3: Host on Lab Server

```bash
mkdocs build
# Copy the site/ folder to your web server
scp -r site/ user@labserver:/var/www/wiki/
```

---

## TODO — Files to Organize and Add

### Neuroventure Data Files

- [ ] Imaging protocol document (TR, TE, slices for each sequence)
- [ ] HeuDiConv heuristics `.py` file — embed in `docs/neuroventure-detailed/data/bids-conversion.md`
- [ ] BIDS validator output `.txt` — attach or embed in `docs/neuroventure-detailed/data/bids-conversion.md`
- [ ] Unusual header information `.csv` — add to `docs/neuroventure-detailed/data/anomalies.md`
- [ ] Scan completion dates `.xlsx` — reference in `docs/neuroventure-detailed/data/anomalies.md`
- [ ] QC during scan notes `.xlsx` — reference in `docs/neuroventure-detailed/data/anomalies.md`
- [ ] Scan file mapping documentation — add to `docs/neuroventure-detailed/data/overview.md`

### CAT12 Files

- [ ] CAT12 MATLAB batch script — embed in `docs/neuroventure-detailed/preprocessing/cat12.md`
- [ ] IQR cutoff values and literature references
- [ ] Protocol for handling multiple T1 scans per session
- [ ] Example IQR report screenshot — drop in `docs/neuroventure-detailed/assets/images/`

### fMRIPrep Files

- [ ] Exact fMRIPrep command with all flags used — add to `docs/neuroventure-detailed/fmriprep/arguments.md`
- [ ] fMRIPrep version number
- [ ] SLURM job submission script — embed in `docs/neuroventure-detailed/fmriprep/setup.md`
- [ ] Batch submission script (loop/array for all subjects)
- [ ] BeautifulSoup HTML parsing script — embed in `docs/neuroventure-detailed/fmriprep/outputs.md`
- [ ] Error summary CSV (19 subjects with errors)

### Denoising Files

- [ ] Nilearn batch processing script — embed in `docs/neuroventure-detailed/denoising/nilearn.md`
- [ ] CONN HPC setup instructions — add to `docs/neuroventure-detailed/denoising/conn.md`

### General Info to Fill In

- [ ] HPC paths: BIDS data location, fMRIPrep outputs, shared scripts, containers
- [ ] PI / contact info for each dataset page
- [ ] Ethics protocol numbers and who to contact for each cohort
- [ ] Lab communication channels (for onboarding page)
- [ ] Data dictionaries for each cohort
- [ ] Publications list per cohort

### Other Cohort Pages (Ask Lab Members to Contribute)

- [ ] Proventure — modalities, N subjects, timepoints, data location
- [ ] Coventure10 — modalities, N subjects, timepoints, data location
- [ ] C-PIP — modalities, N subjects, timepoints, data location
- [ ] Coventure (behavioral) — measures, N subjects, timepoints
- [ ] Univenture — measures, N subjects, timepoints
- [ ] CUSP — measures, N subjects, timepoints
- [ ] Nutriventure — measures, N subjects, timepoints
- [ ] Opiventure — measures, N subjects, timepoints

---

## Git Workflow for Contributors

```bash
# Clone the repo
git clone <repo-url>
cd lab-wiki

# Create a branch for your changes
git checkout -b add-proventure-info

# Make edits to markdown files
# Preview with: mkdocs serve

# Commit and push
git add docs/datasets/neuroimaging/proventure.md
git commit -m "Add Proventure dataset info"
git push -u origin add-proventure-info

# Open a pull request on GitHub
```
