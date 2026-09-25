# Hands-on Workshop: From Flood Mapping to Critical Infrastructure Accessibility

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sesac-sweden/beginner-eo-analysis-series-2026/blob/main/day-2/02-flood-accessibility-workshop/sweden_2020_flood_accessibility_final.ipynb)
![License](https://img.shields.io/badge/code-MIT-blue)

A hands-on Earth Observation workshop that follows a real flood event from start to finish: from a raw Sentinel-1 radar signal, to a flood map, to identifying affected roads, and finally to examining how flooding can disrupt access to critical infrastructure.

The workshop was developed for the **SESAC Beginner Earth Observation Analysis Series**, held in Lund, Sweden, in September 2026.

**Instructors:** Stefanos Georganos & Amalia Chantziara

---

## The case study

In February 2020, storms Ciara and Dennis brought sustained, heavy rainfall to southwestern Sweden. Sweden's Civil Contingencies Agency (MSB) requested Copernicus Emergency Mapping — activation **EMSR427** — which covered 12 areas across roughly 41,200 km² of southern Sweden.

This notebook focuses on one of those areas: the **Viskan river valley**, from **Borås** to **Skene**, in Sjuhärad.

The study area is deliberately widened to include both **Södra Älvsborgs Sjukhus (SÄS)** hospital sites in Borås and Skene.

The exercise moves beyond identifying where flooding occurred to ask a broader societal question:

> **What happens to access to essential services when parts of the road network are affected by flooding?**

---

## What the notebook does

The practical exercise follows a complete analytical workflow:

1. **Satellite data**  
   Retrieves a before/during pair of Sentinel-1 SAR images over the flood period.

2. **Flood detection**  
   Converts the radar signal into a binary flood mask using a simple and transparent two-condition approach: an absolute threshold combined with a significant decrease from the baseline observation.

3. **Roads and critical infrastructure**  
   Retrieves the road network and four categories of critical facilities — hospitals, fire stations, police stations and schools — from OpenStreetMap and examines their intersection with the flood extent.

4. **Accessibility analysis**  
   Builds a road-network graph and evaluates how much of the network is reachable within 5, 10 and 15 minutes of each facility category under normal and flooded conditions.

5. **Exposure and interpretation**  
   Compares the results with population data from Statistics Sweden (SCB) and land-cover information from NMD2018 to explore potential exposure and help interpret the flood-detection results.

The practical workflow can be summarised as:

**Earth Observation and flood information → spatial data integration → affected infrastructure → accessibility analysis → interpretation**

No previous programming experience is required. The notebook contains pre-written code cells that participants can run sequentially while focusing on understanding the workflow and interpreting the outputs.

---

## Workshop materials

This folder contains:

```text
02-flood-accessibility-workshop/
├── README.md
├── sweden_2020_flood_accessibility_final.ipynb
├── flood-accessibility-workshop.pdf
├── population.tif
├── landcover.tif
└── LICENSE
```

- **`sweden_2020_flood_accessibility_final.ipynb`** — Google Colab/Jupyter notebook used for the practical exercise
- **`flood-accessibility-workshop.pdf`** — presentation accompanying the workshop
- **`population.tif`** — SCB 1 km population grid, pre-clipped to the study area
- **`landcover.tif`** — NMD2018 land-cover raster, pre-clipped to the study area
- **`LICENSE`** — MIT licence covering the workshop code

---

## Data sources

| Data | Source | Account needed? |
|---|---|---|
| Sentinel-1 GRD SAR (VH) | Copernicus Data Space Ecosystem / Sentinel Hub | **Yes** — free CDSE OAuth client |
| Roads and critical facilities | OpenStreetMap (`osmnx`) | No |
| Population grid | Statistics Sweden (SCB), 1 km grid | No |
| Land-cover raster | NMD2018, Naturvårdsverket | No |

Only the Sentinel-1 retrieval step requires an account. The other resources required for the exercise are either retrieved automatically or included with the workshop materials.

---

## How to run the exercise

1. Click the **Open in Colab** badge at the top of this page.

2. If you do not already have one, create a free account with the [Copernicus Data Space Ecosystem](https://dataspace.copernicus.eu).

3. Create a Sentinel Hub OAuth client:

   **Profile icon → Sentinel Hub → User Settings → OAuth clients → Create**

4. Run the notebook cells from top to bottom.

5. When prompted, enter your **Client ID** and **Client Secret**.

   The credentials are entered interactively using `getpass` and are not stored in the notebook.

6. If Google Colab asks you to restart the runtime after the initial package installation, restart it and continue with the subsequent cells.

---

## Data and licensing

The workshop combines datasets from several external providers. Their original licences and terms of use continue to apply.

- **Sentinel-1 / Copernicus Data Space Ecosystem** — © European Union, Copernicus Sentinel data
- **Roads and critical facilities** — © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors, ODbL
- **Population grid** — Statistics Sweden (SCB)
- **Land cover (NMD2018)** — Naturvårdsverket, CC0

The **code associated with this workshop is shared under the MIT License**. The external datasets retain their respective original licences and terms of use.

---

## Author and acknowledgements

Workshop material and notebook developed by:

**Amalia Chantziara**  
SESAC Project Assistant

The workshop forms part of the **SESAC Beginner Earth Observation Analysis Series** and was delivered by **Stefanos Georganos and Amalia Chantziara**.

SESAC — the **Swedish Competence Centre for Satellite-Enabled Social Science Analytics** — is funded by the **Swedish National Space Agency (Rymdstyrelsen)**.

🌐 [sesac.se](https://sesac.se)

---

*If you use or adapt this notebook, a link back to the SESAC repository is appreciated.*
