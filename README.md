# Mars Geophysics Portfolio — Noctis Mons Investigation

This repository contains computational geophysics and geodynamics projects completed during a planetary science internship at the **Institute of Planetary Research, German Aerospace Center (DLR), Berlin**, under the supervision of Dr. Adrien Broquet. The Python-based orbital data analysis developed here, along with numerical models, underpin a Master's thesis published and accessible via ESSOAr.

--

## Publication
>
> [Full record — eLibrary DLR](https://elib.dlr.de/222060/) 📚 &nbsp;|&nbsp; Open Access, DLR - Research area:	Raumfahrt| EW - Space Exploration| Research theme (Project)- Exploration of the Solar System, Planetary Evolution and Life
>
> **Beg, F.** (2025). *Geophysical Investigation of Noctis Volcano on (equatorial) Mars using MOLA, MARSIS, and Numerical Plume Modelling.* Master's Thesis, University of Nantes. DOI: [10.22541/essoar.176218868.89744519/v1](https://dx.doi.org/10.22541/essoar.176218868.89744519/v1)
---
## Research Summary
Noctis Mons is a recently identified, heavily fractured shield volcano located in equatorial Mars between Noctis Labyrinthus and Valles Marineris. This work reconstructs its pre-fracture topographic structure, quantifies ancient plume-induced crustal uplift, and analyses subsurface radar data to constrain the composition of the volcanic edifice. Key findings include:
- Reconstructed volcanic height of **~8694 m** above the pre-volcanic surface
- Mantle plume head estimated at **~470 km wide** and **~70 km thick**
- Subsurface basalt porosity of **~51%**, suggesting explosive volcanic activity and possible phreatomagmatism driven by interaction with Valles Marineris water during the Hesperian
---
## Getting Started

### Requirements
- **Python 3.11** (developed and tested on Python 3.11 via Anaconda)
- **Jupyter Notebook** or **JupyterLab** (or open `.ipynb` files directly in VS Code with the Jupyter extension)

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/moztarib/mars-geophysics-portfolio.git
cd mars-geophysics-portfolio
```

**2. Create a conda environment (recommended)**
```bash
conda create -n mars-geo python=3.11
conda activate mars-geo
```

**3. Install the required libraries**
```bash
pip install numpy scipy matplotlib geopandas pyshtools shapely jupyter
```
> ⚠️ `pyshtools` is best installed via conda to avoid build issues:
> ```bash
> conda install -c conda-forge pyshtools
> ```

### How to Run

**Jupyter Lab/Notebook**
```bash
jupyter lab
```
Navigate to the project folder (e.g. `01-MOLA-volcanic-reconstruction/`) and open the `.ipynb` file.

---
## Projects
### 1. `01-MOLA-volcanic-reconstruction/` — MOLA Topographic Analysis & Surface Reconstruction
Extracts a ~2000 km regional DEM around Noctis Mons from the MOLA spherical harmonic model. Multi-azimuth radial elevation profiles are used to identify the lateral extent of volcanic uplift, cross-referenced against tectonic fault maps. The volcanic construct is masked and the pre-volcanic surface is reconstructed via RBF interpolation.

---
###  2. `02-MARSIS-radargram-analysis/` — MARSIS Radargram Analysis and Subsurface compositional modelling
Processing and interpretation of Mars Advanced Radar for Subsurface and Ionosphere Sounding (MARSIS) data over the Noctis Mons region. Includes radargram visualisation, signal processing, and derivation of subsurface dielectric properties used to estimate basalt porosity.

---
### 3. `03-DSP_Plume-modeling/` - Numerical Modeling: Plume supported Dynamic Uplift
Analytical elastic flexure modelling of plume-induced crustal uplift beneath Noctis Mons. Constrains mantle plume dimensions by fitting predicted surface deformation to the observed topographic signal.

---
## Technical Skills Demonstrated
- Large-scale raster data processing and dataset integration (MOLA, MARSIS)
- Quantitative spatial modelling and numerical analysis at scale (spherical harmonics, DEM)
- Geospatial data analysis and GIS workflow automation (GeoPandas, QGIS)
- Data interpolation and reconstruction from sparse inputs (RBF, spline methods)
- Signal processing and inverse problem solving (radar dielectric inversion)
- Analytical physical modelling and scenario testing (elastic flexure)
- Data visualisation and insight communication (Matplotlib, 3D surface plots)

---

## Tools & Libraries
Python, Jupyter Notebook, NumPy, SciPy, Matplotlib, GeoPandas, pyshtools, Shapely, QGIS
---
**Author:** Faris Beg &nbsp;·&nbsp; [ORCID 0009-0007-6945-0893](https://orcid.org/0009-0007-6945-0893)  
**Institution:** Institute of Planetary Research, DLR Berlin &nbsp;|&nbsp; University of Nantes  
**Supervisor:** Dr. Adrien Broquet, DLR Berlin  
**Period:** January 2025 – June 2025
