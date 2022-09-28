# Measuring McCities: Landscapes of Chain and Independent Restaurants in the United States

## Project background

## Data 
Our raw data come from LeadsDeposit. The data was collected April, 2021. We mainly cleaned the raw data through correcting the restaurant names (e.g., Cold St1 Creamery -> Cold Stone Creamery) and merging chain branches (e.g., Waffle House 4245 -> Waffle House). We also spatial joined the restaurant data with county and urban area shapefiles. Thus, our final data has the following columns: 

* **RestaurantName**: Restaurant name (processed)
* **Cusine**: Restaurant cuisine (raw)
* **OpenHours**: Restaurant's open hours (raw)
* **CNTY_NAME**: The name of the county where the restaurant is located (processed)
* **UA_NAME**: The name of the urban area where the restaurant is located (processed)
* **Lon**: The longitude of the restaurant, projected to WGS84, crs=4326 (processed)
* **Lat**: The latitude of the restaurant, projected to WGS84, crs=4326 (processed)
* **Frequency**: The frequency of the restaurant (processed)
* **isChain**: A binary indicator that is 1 if the restaurant frequency > 5 else 0 (processed)

In total, our data has 705,622 restaurants, within which 392,078 are independent restaurants (frequency == 1). The highest chainness restaurant is Subway, with a frequency of 24333. To see the geographic distribution of data and explore its attributes, you can go to our [interactive chainness map](https://friendlycities-gatech.github.io/chainness/). 

**You can download the csv data [here](https://github.com/friendlycities-gatech/chainness/tree/main/data)**. The full dataset needs to merge part 1 and part2. Note that the geojson file in the same folder is only used for interactive visualization, in which the actual location of the restaurants may be coarsened and some data points are removed for quicker rendering. Please refer to the csv for the accurate analysis. This data is curated specifically to examine the chain and independent foodscape in the United States and thus users should use with discretion. The data is shared for non-profit and academic uses and you must cite the sources (see below). 

## Method 
We use **Frequency** and **isChain** to measure the chainness of a restaurant on the point level. 

**Frequency** refers to the number of occurences of a restaurant name in the United States, i.e., how many of the resturants have the same name. This variable has a long-tail distribution, with many independent restaurants valued at 1 and few chain restaurants valued beyond 5000. The maximum frequency is Subway with 24333 outlets. Though we cleaned the restaurant names in the raw data, the exact number of the frequency may not be accurate. 

**isChain** is a binary decision on whether the restaurant has more than five outlets. We defined this threshold using domain knowledge of logistics—such that a restaurant owner of a small franchise could visit and manage his or her locations in one day. This variable is useful when averaged on the county, UA, or MSA levels to represent the percentage of chain restaurants in an area. 

To see the effects of other chainness measures and the correlations of a place's chainness and socioeconomic/built environment variables (e.g., walkability, race, education, political orientation, access to highway etc.), please refer to our open access publication: [Measuring McCities: Landscapes of Chain and Independent Restaurants in the United States](https://journals.sagepub.com/doi/full/10.1177/23998083211014896)

## Citation 
If you use this dataset and our metrics, please cite the data source and publication: 

LeadsDeposit. (2021). *WebMaster* [Data set]. https://leadsdeposit.com/

Liang, X., & Andris, C. (2022). Measuring McCities: Landscapes of chain and independent restaurants in the United States. *Environment and Planning B: Urban Analytics and City Science, 49*(2), 585-602.
