# MARSIS Radargram Analysis

## Overview
Processing and analysis of Mars Advanced Radar for Subsurface and Ionosphere Sounding (MARSIS) radargram data over the Noctis Mons region. The notebook extracts calibrated radar echoes from raw NASA PDS4 binary files, isolates subsurface reflectors from surface clutter, and estimates the dielectric constant and composition of the subsurface material.

## Methodology
- Parsing of PDS4 XML metadata to extract image dimensions and calibration parameters
- Loading and reshaping of raw binary `.img` files into a calibrated 2D radargram
- Georeferencing via `_geom.tab` geometry files (latitude, longitude, UTC time)
- Overlay of clutter simulation to distinguish subsurface echoes from surface returns
- Interactive point selection on a thickness grid for dielectric constant estimation: ε = (ct/2H)²
- Two-component compositional mixing model (Stillman et al. 2010) — basalt vs. ice and basalt vs. void

## Key Files
- `marsis-analysis.ipynb` — Main analysis notebook
- `requirements.txt` — Python dependencies

## Data Sources
- Raw MARSIS orbit files (`o_04884`) via the [NASA ODE Portal](https://ode.rsl.wustl.edu/mars/) — instrument **MARSIS**, product type **EDRSAR**
- Supporting data files archived on Zenodo: [INSERT DOI HERE]

| File | Size | Description |
|---|---|---|
| `MOLA_GLobalGrid_saved_lmax3000.npy` | 275 MB | Global MOLA elevation grid — context map. Zenodo only, not in repo. |
| `grid_noctis.npy` | 114 kB | Noctis Mons regional elevation grid |
| `difference_grid.npy` | 114 kB | Present-day topography minus reconstructed base surface |
| `line_data.npz` | 20 kB | Pre-extracted radar line profiles |

> Update the `folder` variable in Section 2b to point to your local PDS4 orbit files.

## Requirements
```
numpy
pandas
matplotlib
geopandas
statsmodels
```
```bash
pip install -r requirements.txt
```
> Section 4 (interactive point selection) requires a local Jupyter environment — `%matplotlib qt` will not work in browser-only setups.

## Reference
Stillman et al. (2010). *New constraints on the dielectric properties of Martian polar layered deposits.* JGR Planets.
