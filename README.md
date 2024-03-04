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
Rice mapping has been done with the SAR data obtained from Sentinel-1. Rice fields have been mapped based on the backscattering value's thresholding technique. The backscatter values used as thresholds are followed by the study of Anuradha et al.[1] 

#### 2. Sensitivity analysis for burned area mapping
Sentinel-2 is an optical sensor that takes images of Earth at 13 different wavelength regions. Utilizing some of the images of the sensor, an index is developed to map burned areas. It is named as Burned Area Index for Sentinel-2 (reference). 

![Formula](https://drive.google.com/uc?authuser=0&id=1BdLa-b8_c1MGKHbcitXFQRL05jO2rJOP&export=download)

There were 123 samples of active fire points in the Punjab state for the date 03/11/2020. Using those points as a reference, the range of BAIS-2 values is found. Sensitivity analysis has been performed with different percentile values of BAIS-2. Burned and unburned field samples are available for the year 2022. They were used for the sensitivity analysis. 50th percentile value had higher true positives and true negatives. Therefore, the 50th percentile value is considered as a threshold in this study.

#### 3. Earth Engine Application for mapping agriculture residue burned area
Based on the harvesting trends of Kharif crops in Punjab, the harvesting dates have been considered to be between September 15 and November 30 of any particular year. The application is built to get the area of rice fields burned during that time period for any particular year from 2019. (Based on Sentinel-2 data availability for the region).

![application](https://drive.google.com/uc?authuser=0&id=1ddwymDhlPxQZnBj6A3J_43ghD0nQqzcW&export=download)

Codes for the separate objectives are given in the folder 'Code'

Data in the 'Data' folder are in .geojson, zip formats. These files have to be uploaded as GEE asset and should be imported while running the code.

All the codes in 'code' folder are written in Google Earth Engine Code Editor.

Initially rice is mapped in this project and that rice layer is further used for crop residue burned area analysis. Reference paper used for writing the code is given in the folder 'docs' folder

The application can be reused for,
1. other study areas.
2. other indices in place of BAIS-2.
3. other time periods.
4. other applications like flood area mapping, places affected by heat stress in a year, etc.

[1](https://www.researchgate.net/publication/335490095_Rice_Acreage_Estimation_of_Ludhiana_District_using_Sentinel-1A_Time_Series_Data)

#### Acknowledgements
This work was done as a part of a summer research program called Nav-i-GEE organized by IIT Tirupati Navavishkar Foundation in collaboration with Google Earth Engine. This work was done in collaboration with CEEW (Council on Energy, Environment and Water). I acknowledge my sincere regards to Dr. Rafiuddin Mohammad who is the mentor for this project.
