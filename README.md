# Dynamic Tool to map agricultural residue burnt area using Sentinel-2
The repository contains information and code about dynamically mapping agriculture residue burned areas by considering study area as Punjab, India.

### Background
Rice is a significant crop grown during the Kharif season in Punjab. As an easy way to clear the agricultural residue to prepare the field for the next season, the farmers in the Indo-Gangetic plain prefer to burn the crop residue. This causes increased air pollution in those states. To get the heat of the situation, it's inevitable to quantify the area burned and which region tops the chart. This application helps to obtain those insights.

The study is divided into four different objectives. 
1)Backscatter analysis for rice mapping
2)Rice mapping
3)Sensitivity analysis for burned area mapping
4)Earth engine application for mapping agriculture residue burned area

Codes for the separate objectives are given in the folder 'Code'

Data in the 'Data' folder are in .geojson, zip formats. These files have to be uploaded as GEE asset and should be imported while running the code.

All the codes in 'code' folder are written in Google Earth Engine Code Editor.

Initially rice is mapped in this project and that rice layer is further used for crop residue burned area analysis. Reference paper used for writing the code is given in the folder 'docs' folder.
