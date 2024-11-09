<img src="https://iittnif.com/images/logos/Logo.png" width="300" align="left">
<img src="https://geospatialmedia.s3.amazonaws.com/wp-content/uploads/2020/07/google-earth-engine.jpg" width="200" align="left">

<p align="left">
  <img src="https://iittnif.com/images/logos/Logo.png" width="200" />
</p>
<p align="right">
  <img src="[https://example.com/right-image.jpg](https://geospatialmedia.s3.amazonaws.com/wp-content/uploads/2020/07/google-earth-engine.jpg)" width="200" />
</p>

# Dynamic Tool to map agricultural residue burnt area using Sentinel-2
The repository contains data and code for dynamically mapping agriculture residue burned areas by considering the study area as Punjab, India.

### Background
Rice is a significant crop grown during the Kharif season in Punjab [1].  As an easy way to clear the agricultural residue to prepare the field for the next season, the farmers in the Indo-Gangetic plain prefer to burn the crop residue. This causes increased air pollution in those states. Especially due to the weather in the months of October and November in Delhi, the smoke doesn't get its way to move further, causing serious impacts to the National Capital Region(NCR). To understand the heat of the situation, it's inevitable to quantify the area burned and which region tops the chart. Satellite data available in Google Earth Engine (GEE) can be used to obtain these insights. This application dynamically maps the total burned area in Punjab using data from GEE.
***
### Methodology followed

The study can be divided into the following sub-sections.
1. Rice mapping
2. Sensitivity analysis for burned area mapping
3. Earth engine application for mapping agriculture residue burned area

#### 1. Rice mapping
Rice mapping was done using the SAR data obtained from Sentinel-1 in this study. Rice fields have been mapped based on the thresholding technique for the backscattering value. The backscatter values used as thresholds are followed by the study of Anuradha et al.[2] 

#### 2. Sensitivity analysis for burned area mapping
Sentinel-2 is an optical sensor that takes images of Earth at 13 different wavelength regions. Utilizing some of the images of the sensor, an index is developed to map burned areas. It is named as Burned Area Index for Sentinel-2 [3].

![Formula](https://drive.google.com/uc?authuser=0&id=1BdLa-b8_c1MGKHbcitXFQRL05jO2rJOP&export=download)

There were 123 samples of active fire points ('Active_fire_points.zip' file in the Data folder) in the Punjab state for the date 03/11/2020. Using those points as a reference, the range of BAIS-2 values is found. A sensitivity analysis was performed with different percentile values of BAIS-2. Burned and unburned field samples are available for the year 2022 ('Rice_fields_coordinates_2022.zip' file in the Data folder). They were used for the sensitivity analysis. 50th percentile value had higher true positives and true negatives. Therefore, the 50th percentile value is considered as a threshold in this study.

#### 3. Earth Engine Application for mapping agriculture residue burned area
Based on the harvesting trends of Kharif crops in Punjab, the harvesting dates have been considered to be between September 15 and November 30 of any particular year. The application was built to get the area of rice fields burned during that time period for any particular year starting in 2019. (Based on Sentinel-2 data availability for the region).

![application](https://drive.google.com/uc?authuser=0&id=1ddwymDhlPxQZnBj6A3J_43ghD0nQqzcW&export=download)

Link for the application - https://ee-dhanasekaraniirs.projects.earthengine.app/view/stubble-burning-mapping

---

The application can be reused for,
1. other study areas.
2. other indices in the place of BAIS-2.
3. other time periods.
4. other applications like flood area mapping, places affected by heat stress in a year, etc.

#### References

[1] Niti Gupta (2019) ‘Paddy Residue Burning in Punjab: Understanding Farmers' Perspectives and Rural Air Pollution’, March. https://www.ceew.in/sites/default/files/CEEW-Paddy-Residue-Burning-in-Punjab-Farmers-Perspectives-Issue-Brief-29Mar19.pdf

[2] Sharma et al. Rice Acreage Estimation of Ludhiana District using Sentinel-1A Time Series Data, Journal of Agricultural Physics, (2019). https://www.researchgate.net/publication/335490095_Rice_Acreage_Estimation_of_Ludhiana_District_using_Sentinel-1A_Time_Series_Data

[3] Filipponi, F. BAIS2: Burned Area Index for Sentinel-2. Proceedings 2018, 2, 364. https://doi.org/10.3390/ecrs-2-05177

---

#### Acknowledgements
This work was done as a part of a summer research program called Nav-i-GEE organized by IIT Tirupati Navavishkar Foundation in collaboration with Google Earth Engine. This work was done in collaboration with CEEW (Council on Energy, Environment and Water). I acknowledge my sincere regards to Dr. Rafiuddin Mohammad, the mentor for this project.
