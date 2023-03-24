# **cliMAKEchange: Changing the Future of Our Great Lakes** 

Team: Angelina Abi Daoud, Olivia Maddigan, and Madinakhon Sulaymonova  

## **Mission Statement**  

Our world is warming up, and we’re facing a global threat. Climate change is defined by extreme variations in meteorological factors such as temperature and weather patterns, which in turn disrupt the usual balance of nature. 

Our large interconnected freshwater system, the Great Lakes, are inevitably being impacted by climate change. The Great Lakes are located in the mid-east region between Canada and the United States, and they make up the largest basin of freshwater in the world. The five Great Lakes are Lakes Superior, Michigan, Huron, Erie, and Ontario. The Great Lakes are crucial to humankind as they account for around 20% of the world's surface freshwater. Ten million Canadians rely on the Great Lakes as a source of drinking water, for livelihood, and recreational purposes.

Adding to their importance, the Great Lakes are an ideal habitat for various wildlife and aquatic species, however; all of our homes are at risk due to climate change. 

The rising temperatures of the Great Lakes cause accelerated evaporation, which in turn causes water levels to decrease. When water levels decrease, the release of sediment-bound nutrients and toxins increases. The drop in water levels also causes decreased dissolved oxygen, especially during periods of ice cover, which is critical for marine flora and fauna. Additionally, warming waters create increased incidences of harmful algal blooms, lead to the decline of cold water species, and enable the success of invasive species. For instance, Zebra mussels have caused major disruptions in native fish populations among all of the Great Lakes. Exacerbating all of these issues is the fact that development and significant shoreline alterations have resulted in a loss of coastal biodiversity and ecological resilience. The shorelines act as a buffer for what enters the lacustrine ecosystem, therefore the deterioration of shoreline zones and wetlands increases the risk of harming the Great Lakes beyond repair.

First Nations Peoples have lived and coexisted with the Great Lakes ecosystem for millennia, pre-dating European settlers by thousands of years. Approximately 120 bands of Indigenous Peoples have occupied the Great Lakes basin over the course of history. A 2018 poll by the International Joint Commission showed that Indigenous respondents are more worried about the health and state of the Great Lakes than non-Indigenous respondents. Despite this, there has been an ongoing struggle for inclusion of Indigenous voices in water governance of the Great Lakes since at least 1972, when Canada and the United States signed the first Great Lakes Water Quality Agreement. Ongoing work is being done by scientists, such as Dr. Deborah McGregor, to highlight how external agencies, institutional researchers, and non-Indigenous individuals can support the meaningful engagement of Indigenous knowledge to protect our Great Lakes. CliMAKEChange believes that there is always more to learn as we strive for truth and reconciliation, and this education is vital for future Indigenous governance of the Great Lakes. Indigenous water governance will be essential to protect the future of our home’s “freshwater seas”.

“If you think that one person can't make a difference, that's not true, because if everybody felt that way we'll go nowhere. If everybody thought ‘my little piece can make a difference’, then cumulatively we make a massive difference.” - Dr. Gail Krantzberg

CliMAKEChange endeavors to make that difference. Through CliMAKEChange, we hope to raise awareness about the issues that our Great Lakes face in the wake of climate change, and to highlight the importance of Indigenous involvement in future management and conservation efforts in the Canadian context. Our app provides a historical comparison factor by bringing awareness through comparing indicators such as dissolved oxygen, surface lake temperatures, and ice cover which reflect climate change-related parameters that have been degrading our lakes. Not only should we try to reverse damage and protect future conservation of our Great Lakes, but a fundamental change in how the lakes are exploited for resources needs to occur if we are to save these ecological wonders for future generations. Join CliMAKEChange as we strive to change the future of our Great Lakes.

## **Canadian Lake Ontario Stress Index: App Description and Features**

The environment is under immense pressure due to climate change, especially sensitive ecosystems such as coastal wetlands. As a result, our Great Lakes are under a lot of stress. A Multi-Criteria Decision Analysis (MCDA) was conducted to determine how stressed the Canadian side of Lake Ontario is to raise awareness and inspire action. A Canadian Lake Ontario Stress Index was calculated based on parameters that were identified as stressful to local ecology and holistic health of Lake Ontario/Oniatarí:io : invasive species, water quality, sediment quality, marine shipping lanes, and monitored beaches. This index is displayed in conjunction with coastal wetlands to emphasize the relationship between the degradation of this sensitive habitat and our stressed coast. Major Canadian cities and First Nations communities are also displayed in the app to highlight the human relationship to this important freshwater treasure.

##### _What are AOCs?_   
This button defines AOCs (Areas of Concern) in the Great Lakes to provide context for the AOC Tour

##### _Areas of Concern (AOC) tour_    
This feature guides the user through a tour of Canada's 5 designated Areas of Concern along Lake Ontario. The tool includes each AOC clickable for the user, as the map zooms in to display Lake Ontario's stress around that AOC. The user can then click on the AOC symbol to learn more about why the area has been particularly vulnerable to environmental degradation.

##### _Wetlands Near Me?_    
Residents of the Lake Ontario watershed may not be aware that an integral ecosystem is in their backyards - coastal wetlands! This feature allows users to define a buffer radius around any address to view wetlands near them. Users are prompted to enter their address, enable their current location, or drop a pin to locate wetlands near them. The default search radius is 5 km, and user can scroll the bar to increase or decrease from 0 km to 15 km. This tool is meant for Lake Ontario residents to realize whether or not they live near a coastal wetland, which are extremely sensitive and ecologically diverse biogems that we must protect. This feature is meant to inspire action to protect your local wetland from the effects of climate change and urban development.

##### _Feature Summary_   
Users can display aggregate data on the side of the map as they scroll through and change extents to reveal: Number of Major Canadian Cities, Number of First Nations Communities, Number of Coastal Wetlands, and Number of AOCs within the map extent. This tool is useful to summarize the numbers of features shown on the map, especially considering how many wetlands there are.

##### _Explore the Multi-Criteria Decision Analysis Factors_   
Users can learn more about which factors went into the calculation of Lake Ontario's stress index. Most of these factors are available as layers in the Layers tool, so users can take a look at their prevalence within Lake Ontario region. The Stress Index Layer displays the calculated MDCA for Lake Ontario, taking into account dominant factors that leave our lake distressed.

## **Calculations**   

Calculations for the Canadian Lake Ontario Stress Index were done following a typical Multi-Criteria Decision Analysis (MCDA) procedure using a Pairwise Comparison Matrix, with the Weighted Overlay Tool. All calculations were made using Microsoft Excel and the Field Calculator in ArcGIS Pro Version 2.8.6.   
The Index was calculated using ?? indicators that were weighted and combined to form the index. The data from which the ?? factors were derived are outlined in detail in Table 2 of the “Geospatial Open Data Sources” section. 

The Euclidian Distance Tool was used to determine distances from hospitals, fire stations, watercourses, and roads. 
The distances to hospitals and firestations matter because in an emergency, it is ideal to be close to emergency responders. Distance to watercourses matters and is worse the closer you are to the water because in an earthquake, streams can cause liquefaction of the soil which can be very damaging. Distance to roads is good because the closer you are to a road, the more opportunity and acess you have to escape.

The Feature to Raster Tool was used to convert the polygon data (population density, ages, lithology, soil type) into raster form. 
Higher population density is bad in the case of an earthquake because more people will be prone to injury in more cramped settings, especially apartment buildings where floors can collapse. Young people and Seniors are more likley to be victims of an earthquake because they are the most vulnerable populations. Lithology is important because types of rocks react differently to earthquakes, as with soil type.

To obtain building heights (taller buildings are more of a risk in earthqukes), the Digital Elevation Model was subtracted from the Digital Surface Model. 

##### _Part 1 - Indicator Standardization_   

The rasters were all put through the Reclassify tool to reclassify the data on a scale of 1 - 10, with 10 being the most susceptible to earthquake risk and 1 being the least. Equal Intervals were used for all datasets.   

##### Part 2 - Assigning weights and weight standardization   

Each indicator was assigned a weight reflective of its proportion to its influence using a Pairwise Comparison Matrix.

###### Table 1. Pairwise Comparison Matrix  
![alt text](https://github.com/oliviamadd/Equapolis/blob/main/img/t1.png?raw=true)

Factor 1 refers to neighbourhoods with high socioeconomic challenges, such as high unemployment and lower incomes. Factor 2 describes neighbourhoods with physical infrastructure challenges, such as low walkability and a low number of healthy food stores. Factor 3 refers to neighbourhoods with acute vulnerabilities, such as higher premature mortality and unnecessary hospitalizations. These factors correspond to the research done by Urban HEARTS@Toronto as common challenges faced by Toronto neighbourhoods, making these factors appropriate for calculating inequity.    

Because the Neighbourhood Equity Index is meant to identify differences between neighbourhoods, the factors explaining the most variance were weighted more heavily. Weights for the 15 indicators (listed in Table 1 above) were derived by the Social Policy Analysis and Research for the City of Toronto based on the Eigenvalues and community consultations [12].   

The composite weight for each indicator was calculated using the following formula, which was done in Microsoft Excel by Team McRaster:   

Indicator Weight =  (Factor Score1 * Eigenvalue1) + (Factor Score2 * Eigenvalue2) + (Factor Score3 * Eigenvalue3)   

#### Sample calculation of the Indicator Weight for Diabetes:   

Indicator Weight =  (0.826 * 5.378) + (0.323 * 3.147) + (0.218 * 2.559)   
				= 6.017   


Once the indicator weights were calculated, they were standardized so the sum of all weightings equal 1, using this formula:     

Standardized Indicator Weight = Indicator Weight / Sum of all Indicator Weights    


#### Sample calculation of the Standardized Indicator Weight for Diabetes:   
Standardized Indicator Weight = 6.017 / 51.213   
= 0.117   

###### Table 2. Final weights (in %) of all 15 indicators   
![alt text](https://github.com/oliviamadd/Equapolis/blob/main/img/t2.png?raw=true)

##### _Part 3 - Calculating the Neighbourhood Equity Index (NEI)_  

Weighted Neighbourhood Equity index was first calculated so that the resulting scores ranged from 0 to 1, where 1 is inequitable and 0 is equitable:  

Weighted Score = Sum of  (Standardized Indicator Value(i) * Standardized Indicator Weight(i))
Where i is one of the 15 indicators   

#### Sample calculation of the Weighted Score for Diabetes (Bridle Path-Sunnybrook-York Mills Neighbourhood):   

Weighted Score = 0.040404 * 0.117   
= 0.169223   


Finally, the scores were reversed and multiplied by 100 so that the final Neighbourhood equity Index would range from 0 to 100, with 0 being least equitable (worst outcomes) and 100 being most equitable (best outcomes):   

Neighbourhood Equity Index = (1- Weighted Score) * 100   

#### Sample calculation of the Neighbourhood Equity Index (Bridle Path-Sunnybrook-York Mills Neighbourhood):   

Neighbourhood Equity Index = (1- 0.169223) * 100
= 83.08   


Note: The equations were provided by the Social Policy Analysis and Research for the City of Toronto, but all calculations were re-done by Team McRaster in Microsoft Excel and the ArcGIS Pro Field Calculator to display the data spatially. The intention of Team McRaster is to display this data in an interactive and transparent manner, to reach the citizens of Toronto and key decision makers.    

## Geospatial Open Data Sources   

Table 3. Data Used for Story Maps and Dashboards
| <b>Data Layer</b> | <b>Data Source</b> |
| --- | --- |
| <b>US Major Cities</br> | Living Atlas, https://services.arcgis.com/P3ePLMYs2RVChkJx/arcgis/rest/services/USA_Major_Cities_/FeatureServer |
| <b>Great Lakes Watershed</b> | glc_esri, https://www.arcgis.com/home/item.html?id=fe80bdd627d343e8b949ab88bc8312a1#overview |
| <b>Great Lakes Shorelines</b> | glc_esri, https://www.arcgis.com/home/item.html?id=d87347457bc84e5c985db9e904b66b10 |
| <b>First Nations Locations (Canada)</b> | Open Government Canada.ca, https://open.canada.ca/data/en/dataset/b6567c5c-8339-4055-99fa-63f92114d9e4 |
| <b>Major Canadian cities</b> | EsriCanadaEducation, https://www.arcgis.com/home/item.html?id=71894d6f009545be863ae4e85b82faa3 |
| <b>Native Territories</b> | native-land, https://native-land.ca/ |
| <b>Coastal Wetlands, 2004</b> | EPA, https://www.arcgis.com/home/item.html?id=35a94fa85c954b36b22c18514e47f307 |
| <b>Great Lakes Water Quality Monitoring and Surveillance Data (Temperature, Dissolved Oxygen used)</b> | ECCC via Datastream, https://datastream.org/en/dataset/85297d0c-4c71-422b-b213-8f1bde19b00e |
| <b>Great Lakes Outline</b> | sparksa_umich, https://www.arcgis.com/home/item.html?id=2de767ba747f4a7d93b45e5dd980402d |
| <b>Great Lakes Ice Cover, mean annual percent coverage</b> | GLAHF, https://www.glahf.org/data/ |
| <b>NOAA Optimum Interpolation 1/4 Degree Daily Sea Surface Temperature (OISST) Analysis, Version 2</b> | NOAA, https://www.ncei.noaa.gov/metadata/geoportal/rest/metadata/item/gov.noaa.ncdc:C00844/html |

Table 4. Canadian Lake Ontario Stress Index Data 
| <b>Data Layer</b> | <b>Data Source</b> |
| --- | --- |
| <b>Shipping Lanes in the Great Lakes</b>| glc_esri, https://www.arcgis.com/home/item.html?id=a4940deebec84fb9b6afa65afcbf891d |
| <b>Cumulative Degree Days</b>| GLAHF, https://www.glahf.org/data/ |
| <b>Invasive Species Data</b> | GLAHF, https://www.glahf.org/data/ |
| <b>Road Density</b>| Ontario GeoHub, https://geohub.lio.gov.on.ca/datasets/mnrf::ontario-road-network-orn-road-net-element/explore?location=43.391575%2C-79.694348%2C10.58 |
| <b>Provincial Water Quality Data</b>| MECP via ECCC, https://osdp-psdo.canada.ca/dp/en/search/metadata/NRCAN-FGP-1-e6c795b6-32fe-42b7-acf7-836e216c05d6 |
| <b>Sediment Quality Data</b> | ECCC, https://osdp-psdo.canada.ca/dp/en/search/metadata/NRCAN-FGP-1-e6c795b6-32fe-42b7-acf7-836e216c05d6 |
| <b>Beach Closures</b>| https://osdp-psdo.canada.ca/dp/en/search/metadata/NRCAN-FGP-1-e6c795b6-32fe-42b7-acf7-836e216c05d6 |
 
## **Reference**   

References 
