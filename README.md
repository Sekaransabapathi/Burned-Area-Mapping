# Dynamic Tool to map agricultural residue burnt area using Sentinel-2
The repository contains information and code about dynamically mapping agriculture residue burned areas by considering the study area as Punjab, India.

### Background
Rice is a significant crop grown during the Kharif season in Punjab (ceew report citation). As an easy way to clear the agricultural residue to prepare the field for the next season, the farmers in the Indo-Gangetic plain prefer to burn the crop residue. This causes increased air pollution in those states. Especially due to the weather in the months of October and November in Delhi, the smoke doesn't get its way to move further, causing serious impacts to the National Capital Region(NCR). To get the heat of the situation, it's inevitable to quantify the area burned and which region tops the chart. To obtain these insights, satellite data available in Google Earth Engine has been used to create an application that dynamically maps the total burned area in Punjab.
***
### Methodology followed

The study can be divided into the following sub-sections.
1. Rice mapping
2. Sensitivity analysis for burned area mapping
3. Earth engine application for mapping agriculture residue burned area
---
#### 1. Rice mapping
Rice mapping has been done with the SAR data obtained from Sentinel-1. Rice fields have been mapped based on the backscattering value's thresholding technique. The backscatter values used as thresholds are followed by the study of Anuradha et al. 
[1](https://www.researchgate.net/publication/335490095_Rice_Acreage_Estimation_of_Ludhiana_District_using_Sentinel-1A_Time_Series_Data "link")

Codes for the separate objectives are given in the folder 'Code'

Data in the 'Data' folder are in .geojson, zip formats. These files have to be uploaded as GEE asset and should be imported while running the code.

All the codes in 'code' folder are written in Google Earth Engine Code Editor.

Initially rice is mapped in this project and that rice layer is further used for crop residue burned area analysis. Reference paper used for writing the code is given in the folder 'docs' folder.
