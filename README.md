# Hydrological Modeling – Clover Creek Watershed

<p align="center">
  <img src="./clover-creek.jpg" alt="Clover Creek Hydrology Map" width="600"/>
</p>

This GIS project uses **ArcGIS Desktop** to model hydrological features of the **Clover Creek watershed** in Arizona, simulating how water flows across the terrain using Digital Elevation Models (DEMs). The project culminates in a comprehensive map layout containing eight hydrological rasters.

---

## Objective

To apply raster-based hydrological modeling techniques in ArcGIS to delineate stream networks, sub-basins, and watershed boundaries using DEM data.

---

## Tools & Technologies

- **ArcGIS Desktop**
- **Spatial Analyst Extension**
- **Hydrology Toolbox**
  - Fill Sinks
  - Flow Direction
  - Flow Accumulation
  - Raster Calculator
  - Stream Order (Strahler)
  - Watershed Tool
- **Raster Surface Tools**
  - Slope
  - Aspect
- **Coordinate System**: inherited from DEM (local UTM assumed)

---

## Map Output Summary

The final layout includes:

- DEM (Digital Elevation Model)
- Slope Raster
- Aspect Raster
- Flow Direction Raster
- Flow Accumulation Raster
- Stream Raster (≥500 accumulation threshold)
- Stream Order Raster (Strahler Method)
- Watershed Segmentation Raster

Each raster layer is in its own dataframe with a dedicated legend.

---

## Key Findings

- **Flow Direction**: Majority of flow is to the southeast.
- **Streams Identified**: 1,849 stream cells detected using a ≥500 threshold.
- **Highest Stream Order**: 5th-order stream observed in the network.
- **Sub-basins**: 17 sub-catchments delineated from the stream segments.
- **Largest Sub-basin**: Contains 6,402 raster cells (~pixel units).

---

## Analysis Workflow

1. **Fill Sinks** in DEM to remove depressions.
2. Generate **Slope and Aspect** rasters from filled DEM.
3. Calculate **Flow Direction** raster.
4. Generate **Flow Accumulation** grid.
5. Define **streams** using Raster Calculator with a ≥500 threshold.
6. Assign **Stream Order** using Strahler Hierarchy.
7. Compute **Stream Links** and delineate **sub-basins** using the Watershed tool.
8. Compose a multi-frame **map layout** showing all outputs.

---

## Date

October 2023  
Created by: Oscar Babin
