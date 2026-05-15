# Flood Risk Analysis in Complex Urban Areas using LiDAR and HAND  
### Population Exposure Estimation for Coastal Flood Scenarios in Maré, Rio de Janeiro

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.11-blue">
  <img src="https://img.shields.io/badge/QGIS-3.34-green">
  <img src="https://img.shields.io/badge/GeoPandas-Geospatial-success">
  <img src="https://img.shields.io/badge/LiDAR-DEM-orange">
  <img src="https://img.shields.io/badge/Status-In%20Development-yellow">
  <img src="https://img.shields.io/badge/License-MIT-lightgrey">
</p>

---

#  Overview

This project investigates flood risk and population exposure in densely populated urban communities of **Maré**, located in **Rio de Janeiro, Brazil**, using:

- LiDAR-derived elevation models
- HAND (Height Above Nearest Drainage)
- Building footprint analysis
- Population estimation by construction density
- Multi-scenario flood simulation

The main objective is to estimate how many people may be affected under different flooding levels caused by sea level rise, tides, and extreme rainfall events.

---

#  Study Area

The analysis focuses on two regions inside the Maré complex:

- **Nova Holanda**
- **Timbau**

Both areas are highly urbanized and vulnerable to flooding events due to:
- low elevation
- proximity to water bodies
- dense population concentration
- limited drainage infrastructure

---

#  Analyzed Regions

##  Nova Holanda

<p align="center">
  <img src="docs\AreaMareNovaHolandaAnalisada.png" width="90%"> 
</p>

---

##  Timbau

<p align="center">
  <img src="docs\AreaMareTimbauAnalisada.png" width="90%">
</p>

---

#  Methodology

The workflow combines geospatial analysis, remote sensing, and flood modeling techniques.

---

## 1️ LiDAR Processing

High-resolution LiDAR elevation data was used to generate Digital Elevation Models (DEM), enabling precise terrain analysis in urban environments.

### Main Steps
- DEM extraction
- CRS standardization
- Raster preprocessing
- Terrain correction

### Technologies
- QGIS
- GDAL

---

## 2️ HAND Model

The project uses the **HAND (Height Above Nearest Drainage)** methodology to identify terrain susceptibility to flooding.

HAND estimates:
- vertical distance to nearest drainage
- water accumulation tendency
- flood-prone lowlands

This approach allows realistic simulation of flood propagation in complex urban terrain.

---

## 3️ Flood Simulation

Different flood levels were simulated progressively.

Examples:
- 150 cm
- 200 cm
- 250 cm
- 300 cm
- 350 cm
- 400 cm

For each scenario:
- inundated regions are identified
- buildings intersecting flooded areas are detected
- affected population is estimated

---

## 4️ Population Exposure Estimation

Population exposure was estimated using:
- building footprints
- construction density
- spatial intersection with flood polygons

The methodology estimates the number of people potentially impacted at each flood level.

---

#  Results

---

#  Nova Holanda — Population at Risk

<p align="center">
  <img src="docs\MareNovaHolandaFloodRisk.png" width="95%">
</p>

### Key Insights
- Flood impact grows rapidly after 225 cm
- More than 30,000 people may be affected under severe scenarios
- Urban density significantly amplifies exposure risk

---

#  Timbau — Population at Risk

<p align="center">
  <img src="docs\MareTimbauFloodRisk.png" width="95%">
</p>

### Key Insights
- Lower flood levels already begin affecting the population
- Risk acceleration becomes critical above 250 cm
- Nearly 10,000 people are exposed in extreme scenarios

---

#  Technical Pipeline

```text
Digital Elevation Model (DEM)
     ↓
HAND Computation
     ↓
Flood Threshold Simulation
     ↓
Flood Polygon Extraction
     ↓
Building Intersection
     ↓
Population Estimation
     ↓
Risk Visualization