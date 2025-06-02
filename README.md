# Powering Brescia — EV Charging Demand and Optimization Project

This repository contains the code, data, and results for a spatial analysis and optimization project focused on estimating electric vehicle (EV) charging demand in the Province of Brescia and identifying optimal locations for charging stations.

---

## Project Structure

The project is organized into five main folders, each representing a key step in the workflow — from raw data cleaning to final optimization — with intermediate datasets and interactive visualizations.

---

### `00 - Data Cleaning`

> **Data preparation and cleaning pipeline.**
> This folder contains raw datasets and scripts used to clean, preprocess, and unify data from multiple sources.

**Key files:**

* `Pulizia dati.ipynb`: Jupyter notebook with data cleaning steps
* `veicoli.xlsx`: vehicle registry data
* `statocivile.xlsx`: demographic data by civil status
* `dataset_unito.xlsx`: unified dataset combining multiple sources
* `altimetrie.xlsx`: altitude and topographic data

---

### `01 - Estimates + Forecast`

> **EV charging demand estimation and scenario analysis.**
> Demand is estimated under three scenarios: current situation, 2030 conservative, and 2030 optimistic.

**Key files:**

* `Previsioni.ipynb`: notebook projecting EV charging demand
* `df_attuale.csv`: demand data for the current scenario
* `df_2030_conservativo.csv`: 2030 conservative scenario data
* `df_2030_ottimistico.csv`: 2030 optimistic scenario data

These datasets feed into subsequent spatial analyses.

---

### `02 - Hexagons`

> **Spatial discretization using hexagonal grids.**
> The territory is divided into hexagonal cells to enable homogeneous spatial aggregation of demand.

**Key files:**

* `Griglia Esagonale.ipynb`: script to generate the hexagonal grid and aggregate demand
* `df_attuale_esagoni.csv`: aggregated demand per hexagon (current)
* `df_2030_conservativo_esagoni.csv`: aggregated demand for conservative scenario
* `df_2030_ottimistico_esagoni.csv`: aggregated demand for optimistic scenario

*Note: from this folder onward, interactive HTML maps visualize key results.*

---

### `03 - Indexes`

> **Calculation of weighted demand indices per hexagon.**
> Demand indices are computed based on territorial factors to prioritize areas for EV infrastructure.

**Key files:**

* `Indici_v1.ipynb`: notebook computing demand indices
* `gdf_finale_ind.gpkg`: indexed demand for the current scenario
* `gdf_2030_conservativo_finale_ind.gpkg`: indexed demand for conservative scenario
* `gdf_2030_ottimistico_finale_ind.gpkg`: indexed demand for optimistic scenario
* `df_brescia.csv`: supporting provincial data

Interactive maps in this folder show spatial patterns of demand indices.

---

### `04 - Model`

> **Spatial optimization of EV charging station locations.**
> Implements a model maximizing coverage of demand while respecting scenario constraints.

**Key files:**

* `Modelli_v1.ipynb`: notebook implementing the optimization model

The results include interactive maps showing optimal station placement.

---

## Final Deliverables

* `Powering_Brescia.pdf`: full project report
* `Powering_Brescia.ppt`: presentation slides
* `Powering_Brescia_Poster.pdf`: project poster

---

## Notes

* The modeling notebook (from version 2) includes a maximum of 10 charging stations per hexagon constraint.
* This constraint does not affect the current scenario due to the limited number of stations, but facilitates consistent application across all scenarios.

---

Se vuoi, posso aiutarti anche a tradurlo in italiano o a preparare una versione più sintetica per il file README.md. Vuoi?
