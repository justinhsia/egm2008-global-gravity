# EGM2008 Global Gravity Project

This repository contains analysis and visualization of the Earth's gravitational field using the **EGM2008 spherical harmonic coefficients**. The goal is to explore global gravity anomalies, compute disturbed gravity potential, and perform geophysical data analysis using Python.

---

## Project Overview

The **Earth Gravitational Model 2008 (EGM2008)** provides spherical harmonic coefficients representing the Earth's gravity field up to degree and order 2190. This project uses these coefficients to:

- Compute the gravitational potential `V` and disturbed potential `T = V - U`
- Visualize low-degree terms (e.g., quadrupole `l=2`) globally
- Analyze spatial patterns and anomalies
- Integrate with geospatial datasets for further analysis

---

## Folder Structure

egm2008-global-gravity/
├── data/ # Small datasets only; GFC file is fetched dynamically
├── notebooks/ # Jupyter notebooks for analysis and visualization
├── src/ # Helper scripts and modules
├── results/ # Figures and outputs from notebooks
├── README.md
└── .gitignore


> **Note:** The `EGM2008.gfc` file is not included due to size constraints. PySHTOOLS downloads it automatically.

---

## Dependencies

- Python 3.9+  
- [NumPy](https://numpy.org/)  
- [Matplotlib](https://matplotlib.org/)  
- [PySHTOOLS](https://shtools.github.io/SHTOOLS/)  
- [Cartopy](https://scitools.org.uk/cartopy/docs/latest/)  
- [GeoPandas](https://geopandas.org/)  

Install via pip:

```bash
pip install numpy matplotlib pyshtools cartopy geopandas


import pyshtools as pysh

# Load EGM2008 model
clm = pysh.datasets.Earth.EGM2008(lmax=360)

# Compute a grid of potential values
grid = clm.expand(lmax=360)

# Visualize low-degree term
grid.plot()


Future Directions / Planned Analysis

Compute disturbed gravity potential T = V - U at various latitudes

Map global gravity anomalies using Cartopy

Overlay geospatial datasets with GeoPandas

Perform clustering or regression analysis to explore patterns

Publish results and visualizations to GitHub

References

Pavlis, N.K., Holmes, S.A., Kenyon, S.C., Factor, J.K., EGM2008: An Earth Gravitational Model to Degree 2190, 2012.

PySHTOOLS Documentation
