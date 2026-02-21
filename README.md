# Mars Geophysics Portfolio — Noctis Mons Investigation

Computational geophysics and geodynamics projects completed during a planetary science internship at the **Institute of Planetary Research, German Aerospace Center (DLR), Berlin**, under the supervision of Dr. Adrien Broquet. This repository contains the Python-based orbital data analysis and numerical modelling underpinning a Master's thesis published and accessible via ESSOAr.

---

## Publication

> **Beg, F.** (2025). *Geophysical Investigation of Noctis Volcano on (equatorial) Mars using MOLA, MARSIS, and Numerical Plume Modelling.* Master's Thesis, University of Nantes. DOI: [10.22541/essoar.176218868.89744519/v1](https://dx.doi.org/10.22541/essoar.176218868.89744519/v1)
>
> 📄 [Full record — German Aerospace Center (DLR) eLibrary](https://elib.dlr.de/222060/) &nbsp;|&nbsp; Open Access, DLR - Research area:	Raumfahrt | R EW - Space Exploration | Research theme (Project):	R - Exploration of the Solar System, R - Planetary Evolution and Life

---

## Research Summary

Noctis Mons is a recently identified, heavily fractured shield volcano located in equatorial Mars between Noctis Labyrinthus and Valles Marineris. This work reconstructs its pre-fracture topographic structure, quantifies ancient plume-induced crustal uplift, and analyses subsurface radar data to constrain the composition of the volcanic edifice. Key findings include:

- Reconstructed volcanic height of **~8694 m** above the pre-volcanic surface
- Mantle plume head estimated at **~470 km wide** and **~70 km thick**
- Subsurface basalt porosity of **~51%**, suggesting explosive volcanic activity and possible phreatomagmatism driven by interaction with Valles Marineris water during the Hesperian

---

## Projects

### 1. `noctis-mons-reconstruction/` — MOLA Topographic Analysis & Surface Reconstruction
*Notebooks: `Point_Distribution_Interpolation_QGIS.ipynb`, `Reconstruction_Volcanic_Surface.ipynb`*

Extracts a ~2000 km regional DEM around Noctis Mons from the MOLA spherical harmonic model. Multi-azimuth radial elevation profiles are used to identify the lateral extent of volcanic uplift, cross-referenced against tectonic fault maps. The volcanic construct is masked and the pre-volcanic surface is reconstructed via RBF interpolation. An uplift grid is computed and integrated over spherical grid-cell areas to estimate the volume of the uplifted terrain.

**Methods:** MOLA SH expansion (`pyshtools`), Radial Basis Function interpolation (`scipy`), great-circle profile extraction, spline detrending, spherical volume integration

---

### 2. MARSIS Radargram Analysis *(coming soon)*

Processing and interpretation of Mars Advanced Radar for Subsurface and Ionosphere Sounding (MARSIS) data over the Noctis Mons region. Includes radargram visualisation, signal processing, and derivation of subsurface dielectric properties used to estimate basalt porosity.

---

### 3. Numerical Plume Modelling *(coming soon)*

Analytical elastic flexure modelling of plume-induced crustal uplift beneath Noctis Mons. Constrains mantle plume dimensions by fitting predicted surface deformation to the observed topographic signal.

---

## Technical Skills Demonstrated

- Planetary remote sensing data processing (MOLA, MARSIS)
- Spherical harmonic expansion and global DEM analysis
- Geospatial data processing and shapefile integration (GeoPandas, QGIS)
- Grid interpolation and surface reconstruction (RBF, spline)
- Radar signal analysis and dielectric property inversion
- Analytical geophysical modelling (elastic flexure)
- Scientific visualisation (Matplotlib, 3-D surface plots, elevation profiles)

---

## Tools & Libraries

Python, Jupyter Notebook, NumPy, SciPy, Matplotlib, GeoPandas, pyshtools, Shapely, QGIS

---

**Author:** Faris Beg &nbsp;·&nbsp; [ORCID 0009-0007-6945-0893](https://orcid.org/0009-0007-6945-0893)  
**Institution:** Institute of Planetary Research, DLR Berlin &nbsp;|&nbsp; University of Nantes  
**Supervisor:** Dr. Adrien Broquet, DLR Berlin  
**Period:** January 2025 – June 2025
