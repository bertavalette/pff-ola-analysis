# [Thesis Title] — Analysis Code

Code used for data analysis in my master's thesis, **"[Thesis Title]"** ([link to thesis / DOI, if available]).

## About

This repository contains the Jupyter notebooks used to analyze simulation and experimental data
for a Pinched Flow Fractionation (PFF) microfluidic module, plus supporting calibration and
diffusion analyses. Raw and processed data are **not included** in this repository.

> **Note:** These notebooks were originally written and run in **Google Colab**, and load data
> from a personal Google Drive folder (`from google.colab import drive`, paths under
> `/content/drive/MyDrive/...`). They are not directly runnable as-is without data and without
> adjusting the data paths — they are shared for transparency and reference rather than as a
> plug-and-play pipeline. See each notebook's first section for the expected data structure.

## Contents

| Notebook | Description |
|---|---|
| `notebooks/calibration_analysis.ipynb` | Converts pressure to volumetric flow rate using fluorescent bead-tracking data (TrackMate/Fiji). Filters bead velocity distributions, compares technical repeats, and produces the final pressure–flow rate calibration curve. |
| `notebooks/COMSOL_PFF_analysis.ipynb` | Analyzes COMSOL numerical simulation outputs of the PFF module: particle size distributions (KDE) per outlet, separation threshold *d★* vs. wash flow rate, and recovery/purity separation metrics. |
| `notebooks/experimental_PFF_analysis.ipynb` | Analyzes experimental PFF device data, aggregated per device: filtering, KDE distributions per design/outlet, per-device *d★*, recovery/purity, and comparison with the COMSOL predictions. |
| `notebooks/diffusion_analysis.ipynb` | Diffusion analysis of GUV, junction, and interfacial-area (IA) tile scan data. |

## Expected data format

Each notebook expects input data as CSV or Excel files (see the "Setup & data loading" section
at the top of each notebook for the exact column names expected). Briefly:

- **calibration_analysis** — TrackMate `.xlsx` export files, one per applied pressure/repeat.
- **COMSOL_PFF_analysis** — COMSOL-exported `.csv` files with particle metrics per flow condition.
- **experimental_PFF_analysis** — per-device/per-run `.csv` files of experimental particle diameters, plus the COMSOL threshold summary as a comparison input.
- **diffusion_analysis** — tile-scan `.csv` files per region (GUV, junction, IA).

## Requirements

See `requirements.txt`. Install with:

```bash
pip install -r requirements.txt
```

## Citation

If you use this code, please cite:

> [Your Name], "[Thesis Title]", Master's thesis, [University], [Year].

## License

See [LICENSE](LICENSE).
