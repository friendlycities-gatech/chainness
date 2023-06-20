# Measuring McCities: Landscapes of Chain and Independent Restaurants in the United States

![Interactive Data Dashboard for Chain Restaurants](dashboard.png)


[TAKE ME TO THE MAP!](https://friendlycities-gatech.github.io/chainness/)

## Project background

Independent restaurants are important for placemaking, cultivating place identity, and creating local culture. We explored which (types of) locales have an independent food culture and which resemble McCities: foodscapes with chains. We used a dataset of nearly 800,000 independent and chain restaurants for the Continental United States and defined a chain restaurant using multiple methods (notably, by the number of restaurants with the same name). We found that car-dependency, low walkability, high percentage voters for Donald Trump (2016), concentrations of college-age students, and nearness to highways were associated with high rates of chainness. McCities are prevalent in the Midwestern and the Southeastern United States. Independent restaurants were associated with dense pedestrian-friendly environments, highly educated populations, wealthy populations, racially diverse neighborhoods, and tourist areas. Low chainness was also associated with East and West Coast cities.

This project is led by Dr. Clio Andris and PhD Xiaofan Liang at Georgia Institute of Technology [Friendly Cities Lab](https://friendlycities.gatech.edu/). You can contact Xiaofan at xiaofan.l@gatech.edu if you have questions or collaboration requests. Our open access paper can be downloaded [here](https://journals.sagepub.com/doi/full/10.1177/23998083211014896). We would like to thank [Washington Post](https://www.washingtonpost.com/business/2022/09/29/chain-restaurant-capitals/), [Bloomberg MapLab](https://www.bloomberg.com/news/newsletters/2021-06-16/maplab-how-many-chain-restaurants-are-in-your-city), [CNN](https://www.cnn.com/videos/politics/2022/10/08/smr-chain-restaurant-regions-vote-trump.cnn), [FiveThirtyEight](https://fivethirtyeight.com/features/the-datasets-were-looking-at-this-week-21/), and [Georgia Public Broadcasting](https://www.gpb.org/news/2022/10/06/which-states-have-the-most-chain-restaurants-georgia-tech-researchers-map-it-out) for covering this work. You can visit the interactive chainness map [here](https://friendlycities-gatech.github.io/chainness/) 

## Data 
The raw data come from LeadsDeposit. The data was collected April, 2021. We mainly cleaned the raw data through correcting the restaurant names (e.g., Cold St1 Creamery -> Cold Stone Creamery) and merging chain branches (e.g., Waffle House 4245 -> Waffle House). We also spatial joined the restaurant data with county, urban area, and metropolitan statistical area shapefiles. Thus, our final data has the following columns: 

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

In total, our data has 705,621 restaurants, within which 392,077 are independent restaurants (frequency == 1). The highest chainness restaurant is Subway, with a frequency of 24333. To see the geographic distribution of data and explore its attributes, see the [interactive chainness map](https://friendlycities-gatech.github.io/chainness/). 

**If you are interested in an academic or nonprofit collaboration using this dataset, please contact us at clio@gatech.edu and/or xiaofan.l@gatech.edu.**

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
