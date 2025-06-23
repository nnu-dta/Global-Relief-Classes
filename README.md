# Global Relief Classes
[![GitHub](https://img.shields.io/github/license/nnu-dta/global-relief-classes)](https://github.com/nnu-dta/global-relief-classes/blob/main/LICENSE)
[![Zenodo](https://zenodo.org/badge/DOI/10.5281/zenodo.15641257.svg)](https://doi.org/10.5281/zenodo.15641257)
[![Publication](https://img.shields.io/badge/paper-accepted-blue)](https://doi.org/10.5194/essd-2024-401)
[![GitHub Repo stars](https://img.shields.io/github/stars/nnu-dta/global-relief-classes?style=social)](https://github.com/nnu-dta/global-relief-classes/stargazers)

A code repo for producing Global Relief Classes using GIS libraries and scripts, written by the Digital Terrain Analysis (DTA) Lab, School of Geography, Nanjing Normal University.

## Overview
This repository contains the code for producing Global Relief Classes, which classifies terrain relief on the Earth's surface into two levels with 1 arc-second resolution. The classification is based on the differences in slope characteristics and is divided into flat terrain and rugged terrain at Level 1 (L1). At Level 2 (L2), flat terrain is further divided into low-altitude, middle-altitude, high-altitude, and very high-altitude flat terrain, while rugged terrain is subdivided into low-relief, gentle-relief, moderate-relief, high-relief, and very high-relief rugged terrain.
[![Global Relief Classes](/img/grc.png)](https://zenodo.org/records/15641257)
## Processing workflow
### Data preprocessing
-  Extracting DEMs in the land areas
-  Reprojection
-  Mosaicing DEMs
### Dividing flat and rugged terrain (L1)
- Calculating slope maps
- Determining slope thresholds
- Extracting flat areas
- Calculating accumulated slope (AS)
- Determining AS thresholds
### Classifying the relief classes in L2
- Extracting relief features (DEMs -> Flow analysis -> drainage networks)
- Constructing simulated base terrain
  - Interacting with flat reliefs
  - Defining boundaries
  - Determining elevation on boundaries
- Calculating surface relief index (SRI)
- Determining SRI thresholds
### Class refinement for L2 classes
- Reclassifying the flat terrain classes by elevation
- Reclassifying the rugged terrain classes by SRI
### Post-processing
- Eliminating incorrect patches
- Eliminating fragmented blocks
- Merging adjacent patches
- Smoothing boundaries
## How to use
### Requirements
- numpy>=1.19.0
- matplotlib>=3.3.0
- rasterio>=1.2.0
- geopandas>=0.9.0
- whitebox>=2.0.0
### Installation
```bash
pip install -r requirements.txt
```
### Usage
- Run the code for the data preprocessing
- Run the code for the dividing flat terrain and rugged terrain in L1
## Data description
Understanding the land surface morphology and its relief components, which record the dynamics of the planet's evolution and interaction of multiple environmental factors, constitutes a critical aspect of Earth system science. However, classified relief and landform data with a resolution of approximately 1 arc-second (approximately 30 m) are lacking at the global scale, which limits the progress of related studies at finer scales.

We utilized several Digital Elevation Models (DEMs) and innovative approaches to classify terrain relief on the Earth's surface into two levels with 1 arc-second. Table 1 provides the meanings and colormaps for the two levels of relief.

In this study, we refer to the two primary surface types as flat terrain and rugged terrain in Level 1 (L1), based on their differences in slope characteristics. These two contrasting relief classes provide essential support for understanding landform processes, analyzing hydrological patterns, and assessing the spatial distribution of human activities across diverse environmental contexts. At Level 2 (L2), the flat terrain retains elevation-based characteristics and is further divided into low-altitude, middle-altitude, high-altitude, and very high-altitude flat terrain. Rugged terrain is subdivided at L2 into low-relief, gentle-relief, moderate-relief, high-relief and very high-relief rugged terrain.

We provide accessible rasterized files, with the coordinate system in WGS84 (EPSG: 3857). The cell values in each raster file represent tertiary landform types. Specifically, the first digit represents a L1 type, and the first two digits represent a L2 type.

Nanjing Normal University produced this dataset with the support of the Deep-time Digital Earth (DDE) International Big Science Program.
## Datasets
- [Zenodo Repo (rasterized version, 1 arc-second)](https://zenodo.org/records/15641257)
- [National Earth System Science Data Center (vectorized version)](https://nnu.geodata.cn/data/datadetails.html?dataguid=28050973505297&docId=119)
## Publications
Yang, X., Li, S., Ma, J., Chen, Y., Zhou, X., Li, F., Xiong, L., Zhou, C., Tang, G. *, and Meadows, M. *: Global basic landform units derived from multi-source digital elevation models at 1 arc-second resolution, Earth Syst. Sci. Data Discuss. https://doi.org/10.5194/essd-2024-401, Accepted, 2025.
## Data license
[CC BY-NC-SA 4.0](https://www.nationalarchives.gov.uk/doc/non-commercial-government-licence/version/2/)
## Code license
MIT
## Contributors
Yang, Xin; Li, Sijin; Ma, Junfei; Chen, Yang; Zhou, Xingyu; Sun, Wenjie; Zhou, Chenghu; Meadows, Micheal; Li, Fayuan; Xiong, Liyang; Tang, Guoan and other members of the DTA Lab, School of Geography, Nanjing Normal University.

## TODO list
- [ ] Add the code for the data preprocessing
  - [x] Add the code for the reprojecting
  - [ ] Reproject the DEMs to (EPSG:9820)
  - [ ] Add the code for the mosaicing
  - [ ] Add the code for the extracting DEMs in the land areas
- [x] Add the code for the dividing flat and rugged terrain in L1
- [ ] Add the code for the classifying the landform types in L2
- [ ] Add the code for the type refinement
- [ ] Add the code for the post-processing
## Contact
[Yang CHEN (陈阳)](https://cubicsyang.github.io/), School of Geography, Nanjing Normal University
## Acknowledgements
Thanks for the WhiteboxTools developers for their great work on the WhiteboxTools library, which is used in this project.
Thanks for the Nanjing Normal University and Deep-time Digital Earth (DDE) International Big Science Program for providing the data and support for this project.

