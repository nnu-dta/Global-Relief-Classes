# GBLU-code
A code repo for producing Global Basic Landform Units using GIS software and scripts.
## Processing workflow
### Data preprocessing
-  Extracting DEMs in the land areas
-  Reprojection
-  Mosaicing DEMs
### Dividing plains and mountains (L1)
- Calculating slope maps
- Determining slope thresholds
- Extracting flat areas
- Calculating accumulated slope (AS)
- Determining AS thresholds
### Classifying the landform types in L2
- Extracting landform features (DEMs -> Flow analysis -> drainage networks)
- Constructing simulated base terrain
  - Interacting with flat landforms
  - Defining boundaries
  - Determining elevation on boundaries
- Calculating surface uplift index (SUI)
- Determining SUI thresholds
### Type refinement for L3
### Post-processing
- Eliminating incorrect hills
- Eliminating fragmented blocks
## Data description
We utilized several Digital Elevation Models (DEMs) and innovative approaches to classify landforms into three levels on the Earth's surface, producing a dataset with a 30-meter resolution. The meanings and colormap for the three levels of landforms are provided in Table 1.

The Level 1 landforms are Flat Landform and Rugged Landform based on the Accumulated slope (AS). Level 2 landforms have 6 types based on the local relief and Level 3 landforms contain 23 types based on the elevation. The three levels are inherited.

We provide accessible rasterized files, with the coordinate system in WGS84 (EPSG: 3857). The cell values in each raster file represent tertiary geomorphologic types. Specifically, the first digit represents a Level 1 landform type, and the first two digits represent a Level 2 landform type.

This dataset was produced by Nanjing Normal University with the support of the Deep Time Digital Earth International Big Science Program.
## Datasets
- [Zenodo Repo (rasterized version, 1 arc-second)](https://zenodo.org/records/13187969)
- [National Earth System Science Data Center (vectorized version)](https://nnu.geodata.cn/data/datadetails.html?dataguid=28050973505297&docId=119)
## Publications
Yang, X., Li, S., Ma, J., Chen, Y., Zhou, X., Li, F., Xiong, L., Zhou, C., Tang, G., and Meadows, M.: Global basic landform units derived from multi-source digital elevation models at 1 arc-second resolution, Earth Syst. Sci. Data Discuss. [preprint], https://doi.org/10.5194/essd-2024-401, in review, 2024.
## Data license
[CC BY-NC-SA 4.0](https://www.nationalarchives.gov.uk/doc/non-commercial-government-licence/version/2/)
## Code license
MIT
## Contributor
Yang, Xin; Li, Sijin; Ma, Junfei; Chen, Yang; Zhou, Xingyu; Zhou, Chenghu; Meadows, Micheal; Li, Fayuan; Xiong, Liyang; Tang, Guoan
## Contact
[Chen, Yang (陈阳)](https://cubicsyang.github.io/), School of Geography, Nanjing Normal Univeristy
