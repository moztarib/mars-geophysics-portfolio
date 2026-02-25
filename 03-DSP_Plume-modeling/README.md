# Numerical Modeling: Plume supported Dynamic Uplift

## Overview
Forward modelling of dynamic surface uplift at Noctis Mons, Mars, driven by a buoyant sub-lithospheric mantle plume. The notebook constructs a Gaussian density anomaly in spherical harmonic space, solves for the resulting lithospheric flexure using the `Displacement_strain_planet` thin-shell solver, and recovers best-fit plume parameters through a 5-D grid search over density contrast (DA), plume radius (PR), elastic thickness (Te), and plume centre location (lat₀, lon₀) by minimising the RMS misfit against a spline-detrended observed uplift profile.

## Methodology
- Loading of MOLA spherical-harmonic topography (Wieczorek et al., 2015) and GMM3 gravity field (Genova et al., 2016) via `pyshtools`
- Construction of a Gaussian density anomaly at the North Pole and rotation to any candidate centre using rotational covariance of the spherically symmetric planet model — reducing `Thin_shell_matrix_nmax` calls from ~5,000+ to 42
- DA linearity exploit: a single linear solve is scaled across all density contrast values, eliminating redundant solves
- RMS misfit computed against a pre-computed spline-detrended observed Noctis uplift profile (`uplift_spline_profile_tectonics.npz`)
- 5-D misfit array collapsed pairwise via `np.min` to produce 2-D marginal misfit maps for parameter interpretation

## Repository Structure
```
noctis-plume-flexure/
│
├── noctis_plume_flexure model.ipynb           # Main notebook
├── requirements.txt                           # Python dependencies
├── README.md                                  # This file
├── LICENSE                                    # License
├── .gitignore                                 # Excludes large data files
│
└── data/
    ├── uplift_grid_updated.npy                # Interpolated Noctis uplift grid
    ├── uplift_spline_profile_tectonics.npz    # Main: Spline-detrended observed profile
    └── raised elevations_2.shp               # QGIS-sampled raised surface points # Please channge the directory path before runnning the notebook
        raised elevations_2.dbf               # (shapefile sidecar files)
        raised elevations_2.shx
        raised elevations_2.prj
```

## Key Files
- `noctis_plume_flexure model.ipynb` — Main notebook
- `requirements.txt` — Python dependencies
- `data/uplift_spline_profile_tectonics.npz` — Sole observed target used in RMS misfit computation

## Data Sources
- MOLA topography and GMM3 gravity loaded at runtime via `pyshtools.datasets.Mars` — no local download required
- Supporting data files archived on Zenodo (Broquet, 2024): [DOI](http://doi.org/10.5281/zenodo.4916799)

| File | Description |
|---|---|
| `uplift_grid_updated.npy` | Interpolated Noctis uplift grid (base surface subtracted) |
| `uplift_spline_profile_tectonics.npz` | Spline-fitted, tectonically detrended 1-D uplift profile |
| `raised elevations_2.shp` | QGIS-sampled raised surface elevation points |

> Update the shapefile path in Section 4a to point to your local copy of `raised elevations_2.shp`.

## Requirements
```
numpy
scipy
matplotlib
geopandas
pyshtools
cmcrameri
Displacement_strain_planet
```
```bash
pip install -r requirements.txt
```
> `Displacement_strain_planet` and `cmcrameri` are also installed inline at the top of the notebook via `!pip` if not already present in your environment.

## References
Broquet, A. (2024). *Displacement_strain_planet: 0.5.0*. Zenodo. http://doi.org/10.5281/zenodo.4916799

Genova, A. et al. (2016). *Seasonal and static gravity field of Mars from MGS, Mars Odyssey and MRO radio science.* Icarus, 272, 228–245.

Wieczorek, M. A. et al. (2015). *MOLA shape model.* In *Planetary Data System.*
