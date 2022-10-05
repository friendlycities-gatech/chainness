# Measuring McCities: Landscapes of Chain and Independent Restaurants in the United States

![Interactive Data Dashboard for Chain Restaurants](dashboard.png)

## Project background

Independent restaurants are important for placemaking, cultivating place identity, and creating local culture. We explored which (types of) locales have an independent food culture and which resemble McCities: foodscapes with chains. We used a dataset of nearly 800,000 independent and chain restaurants for the Continental United States and defined a chain restaurant using multiple methods (notably, by the number of restaurants with the same name). We found that car-dependency, low walkability, high percentage voters for Donald Trump (2016), concentrations of college-age students, and nearness to highways were associated with high rates of chainness. McCities are prevalent in the Midwestern and the Southeastern United States. Independent restaurants were associated with dense pedestrian-friendly environments, highly educated populations, wealthy populations, racially diverse neighborhoods, and tourist areas. Low chainness was also associated with East and West Coast cities.

This project is led by Dr. Clio Andris and PhD Xiaofan Liang at Georgia Institute of Technology [Friendly Cities Lab](https://friendlycities.gatech.edu/). Our open access paper can be downloaded [here](https://journals.sagepub.com/doi/full/10.1177/23998083211014896). You can interact with our data visualization dashboard [here](https://friendlycities-gatech.github.io/chainness/). We would like to thank our media partners [Bloomberg MapLab](https://www.bloomberg.com/news/newsletters/2021-06-16/maplab-how-many-chain-restaurants-are-in-your-city) and [Washington Post](washingtonpost.com/business/2022/09/29/chain-restaurant-capitals/?pwapi_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWJpZCI6IjMxMTY0NDc1IiwicmVhc29uIjoiZ2lmdCIsIm5iZiI6MTY2NDUzNjIzMCwiaXNzIjoic3Vic2NyaXB0aW9ucyIsImV4cCI6MTY2NTc0NTgzMCwiaWF0IjoxNjY0NTM2MjMwLCJqdGkiOiJmZjlmZDI4Zi1lYjRmLTRmZGEtODY1NS0xNzlkNmZmYzlmYzkiLCJ1cmwiOiJodHRwczovL3d3dy53YXNoaW5ndG9ucG9zdC5jb20vYnVzaW5lc3MvMjAyMi8wOS8yOS9jaGFpbi1yZXN0YXVyYW50LWNhcGl0YWxzLyJ9._tx8XDmZWM4JI-p6dUyVioU7T6imoddZPJowNCS8ryE) for covering our stories. 

## Data 
We released a different dataset than what we used in the paper because the new data is more recent and more open to share to the public. We rerun the analyses on the new data and the conclusions are the same. The released raw data come from LeadsDeposit. The data was collected April, 2021. We mainly cleaned the raw data through correcting the restaurant names (e.g., Cold St1 Creamery -> Cold Stone Creamery) and merging chain branches (e.g., Waffle House 4245 -> Waffle House). We also spatial joined the restaurant data with county, urban area, and metropolitan statistical area shapefiles. Thus, our final data has the following columns: 

* **RestaurantName**: Restaurant name (processed)
* **Cusine**: Restaurant cuisine (raw)
* **OpenHours**: Restaurant's open hours (raw)
* **State**: State (raw)
* **CNTY_GEOID**: County GEOID, which can be joined with other datasets (processed)
* **CNTY_NAME**: The name of the county where the restaurant is located (processed)
* **UA_GEOID**: Urban area GEOID, which can be joined with other datasets (processed)
* **UA_NAME**: The name of the urban area where the restaurant is located (processed)
* **MSA_GEOID**: Metropolitan statistical area GEOID, which can be joined with other datasets (processed)
* **MSA_NAME**: The name of the metropolitan statistical area where the restaurant is located (processed)
* **Lon**: The longitude of the restaurant, projected to WGS84, crs=4326 (processed)
* **Lat**: The latitude of the restaurant, projected to WGS84, crs=4326 (processed)
* **Frequency**: The frequency of the restaurant (processed)
* **isChain**: A binary indicator that is 1 if the restaurant frequency > 5 else 0 (processed)

In total, our data has 705,622 restaurants, within which 392,078 are independent restaurants (frequency == 1). The highest chainness restaurant is Subway, with a frequency of 24333. To see the geographic distribution of data and explore its attributes, you can go to our [interactive chainness map](https://friendlycities-gatech.github.io/chainness/). 

**You can download the csv data [here](https://github.com/friendlycities-gatech/chainness/tree/main/data)**. The full dataset needs to merge part1, part2, and part3. Note that the geojson file in the same folder is only used for interactive visualization, in which the actual location of the restaurants may be coarsened and some data points are removed for quicker rendering. Please refer to the csv for the accurate analysis. This data is curated specifically to examine the chain and independent foodscape in the United States and thus users should use with discretion. **The data is shared for non-profit and academic uses and you must cite the sources (see below)**. 

## Method 
We use **Frequency** and **isChain** to measure the chainness of a restaurant on the point level. 

**Frequency** refers to the number of occurences of a restaurant name in the United States, i.e., how many of the resturants have the same name. This variable has a long-tail distribution, with many independent restaurants valued at 1 and few chain restaurants valued beyond 5000. The maximum frequency is Subway with 24333 outlets. Though we cleaned the restaurant names in the raw data, the exact number of the frequency may not be accurate. 

**isChain** is a binary decision on whether the restaurant has more than five outlets. We defined this threshold using domain knowledge of logistics—such that a restaurant owner of a small franchise could visit and manage his or her locations in one day. This variable is useful when averaged on the county, UA, or MSA levels to represent the percentage of chain restaurants in an area. 

To see the effects of other chainness measures and the correlations of a place's chainness and socioeconomic/built environment variables (e.g., walkability, race, education, political orientation, access to highway etc.), please refer to our open access publication: [Measuring McCities: Landscapes of Chain and Independent Restaurants in the United States](https://journals.sagepub.com/doi/full/10.1177/23998083211014896)

## Citation
If you use this dataset and our metrics, please cite the data source and publication: 

LeadsDeposit. (2021). *WebMaster* [Data set]. https://leadsdeposit.com/

Liang, X., & Andris, C. (2021). Measuring McCities: Landscapes of chain and independent restaurants in the United States. *Environment and Planning B: Urban Analytics and City Science, 49*(2), 585-602. https://doi.org/10.1177/23998083211014896

## Acknowledgements
We would like to thank Sichen Jin and Maggie Zou for their helps on visualizing the data. 
