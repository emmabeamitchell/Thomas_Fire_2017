# False Color Imagery of Thomas Fire

#### Emma Bea Mitchell | December 3rd, 2014


<img title="Thomas Fire credit of Ray Ford / Noozhawk" alt="Picture of the Thomas Fire" src="https://news.ucsb.edu/sites/default/files/styles/large_2340x1212/public/2023-11/Thomas-Fire-Faria-Beach-cropped-Noozhawk.jpg?itok=YGnOu1vN">
Credit to Ray Ford/ Noozhawk

## About: 
### About the Project:

The purpose of this project is to analyze both `AQI` and `landsat` data from the Santa Barbara County area to explore the fire's effects. 

First, we look at `AQI` data from 2017 and 2018, subsetting specifically for Santa Barbara County, and creating a `rolling mean`, which allows us to create a graph visualizing the spike is Air Quality Index at the time of the fire. 

Second, we explore `landsat` data, using both true and false color imagery to show the benefits of using false color imagery. We used the `landsat` data, combined with the `thomas_fire` data to map the effects of the fire. 


Highlights include:
- date and string data wrangling
- visualizing time series
- use of the `.rolling` function to find averages
- use of `.loc` for spatial subsetting
- use of `.squeeze` and `.drop_vars` to remove bands
- load and explore data with `rioxr.open_rasterio()`
- clip one dataset to another using `.rio.clip_box`
- creation of true and false imagery
- crs transformation

### About the data:

The `AQI` data is updated twice a year by the EPA. It contains Air Quality Index data by day, year, and county. It is from a collection of pregenerated data from outdoor monitors across the US. The data was retrieved from [the EPA website](https://aqs.epa.gov/aqsweb/airdata/download_files.html)

The `landsat` data is a simplified collection of bands (red, green, blue, near-infrared and shortwave infrared) from the Landsat Collection 2 Level-2 atmosperically corrected surface reflectance data, collected by the Landsat 8 satellite. The data was retrieved from the [Microsoft Planetary Computer Data Catalogue](https://planetarycomputer.microsoft.com/dataset/landsat-c2-l2) and pre-processed to remove data outside land and coarsen the spatial resolution. 

The `Thomas_fire` data is a subset of the shapefile from [California Fires (all) from Data.gov](https://catalog.data.gov/dataset/california-fire-perimeters-all-b3436), which contains fire data for all of California. This data is updated annualy by The California Department of Forestry and Fire Protection's Fire and Resource Assessment Program.

### References:

Microsoft Planetary Computer Data Catalogue, Landsat collection 2 Level-2. Available from: https://planetarycomputer.microsoft.com/dataset/landsat-c2-l2. Access date: December 3rd, 2024.

Data.gov Data Catalogue, California Fire Perimeters (all). Available from: https://catalog.data.gov/dataset/california-fire-perimeters-all-b3436. Access date: December 3rd, 2024.

AirData, US EPA. Available from:  https://aqs.epa.gov/aqsweb/airdata/download_files.html. Access date: December 3rd, 2024


## Repository Organization
``` python
eds220-hwk4/
│
├── README.md                     
├── Thomas_fire_post.ipynb                      
├── .gitignore                    
├── landsat_map_thomas_fire.png
|
|
├── data/
│   ├── California_Fire_Perimeters_(all).cpg
│   ├── California_Fire_Perimeters_(all).dbf
│   ├── California_Fire_Perimeters_(all).prj
│   ├── California_Fire_Perimeters_(all).shp
│   ├── California_Fire_Perimeters_(all).shp.xml
│   ├── California_Fire_Perimeters_(all).shx
│   ├── California_Fire_Perimeters_(all).geojson
|
```
## Acknowledgements:

Open access data from Data.gov, EPA, and Microsoft Planetary Computer Data Catalogue were integral in this project

Adapted from instructions provided by Carmen Galaz García in EDS 220 Working With Environmental Datasets, a graduate environmental data science class at the Bren School of Environmental Science and Management at UCSB. 

My completion of this project is also due to the help from Carmen Galaz García, Annie Adams, and my fellow peers in the MEDS program at UCSB