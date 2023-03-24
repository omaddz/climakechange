# **cliMAKEchange: With Great Lakes Comes Great Responsibility** 

Team: Angelina Abi Daoud, Olivia Maddigan, and Madinakhon Sulaymonova  

## **Mission Statement**  

Missing

## **App Description and Features**   
## **cliMAKEchange Lake Stress Index**

How is Lake Onrario doing?

## **Lake Stress Index Web App**

Designed to communicate risk factors associated with vulnerability to earthquakes. A Multi-Criteria Decision Analysis (MCDA) was conducted to determine the top 10 most vulnerable areas in Hamilton, as well as rank the vulnerability of each Hamilton census tract. 

##### _Top 10 Earthquake-Vulnerable Zones_   
This feature helps the user pinpoint and navigate through the top 10 most earthquake-vulnerable zones in Hamilton identified through the MCDA.
The tool includes each Zone, from 1 to 10, clickable for the user with the corresponding zone's colour. The user will then be taken directly to the zone of their choosing, where they can then click on the zone and receive a summary of earthquake vulnerability of the area.

##### _Search Your Address_    
Residents of Hamilton can search their address in the search bar.
The user will be taken directly to their address, and can then view which level of vulnerability exists in their community, as well as find out if they live within one of the top 10 most vulnerable zones.
User can also allow the browser to use your location to automatically take you to your current location.

##### _Explore the Multi-Decision Criteria Factors_    
Users can explore the criteria that went into calculating the vulnerability of Hamilton to earthquakes.
In the Layers tool, users can turn layers on and off to compare these different social, environmental, and physical factors to the vulnerability value of their community.
This allows users to interact with the underlying data that went into the calculation, and see how these factors play into earthquake risk and safety.

##### _What's displayed on the map?_   
The top 10 most earthquake-vulnerable regions in Hamilton are shown in purple, with the darkest purple showing Rank 1 (Most vulnerable) and the lightest purple showing Rank 10 (Still vulnerable compared to other parts of Hamilton but the least out of the top 10)
The Vulnerability layer displays the calculated MCDA per census tract in Hamilton, taking into account the social, environmental, and physical factors discussed above. The dark rest depicts Hamilton's most vulnerable census tracts, with the lighter reds depicting less vulnerable zones.

## **Calculations**   

Calculations for the Hamilton Vulnerability Index were done following a typical Multi-Criteria Decision Analysis (MCDA) procedure using a Pairwise Comparison Matrix, with the Weighted Overlay Tool. All calculations were made using Microsoft Excel and the Field Calculator in ArcGIS Pro Version 2.8.6.   

The Index was calculated using 12 indicators that were weighted and combined to form the index. The data from which the 12 factors were derived are outlined in detail in Table 2 of the “Geospatial Open Data Sources” section. 

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

Table 3. Historical Earthquake Data
| <b>Data Layer</b> | <b>Data Source</b> |
| --- | --- |
| <b>Provinces and Territories of Canada</br> | esri_canada |
| <b>Earthquakes in Canada</b><br>(1985-2019) | Government of Canada; Natural Resources |
| <b>Significant Canadian earthquakes</b><br>(1600-2006) | GEOSCAN
Geological Survey of Canada |

Table 4. Multi-Criteria Decision Analysis and eastQUAKE Vulnerability Data.
| <b>Data Layer</b> | <b>Data Source</b> |
| --- | --- |
| <b>Population Density in 2016 by CT</b>| City of Hamilton https://open.hamilton.ca/datasets/3470c8be2fd64103a774c6ad857dbbcc_2/explore |
| <b>Hamilton CTs</b>| City of Hamilton |
| <b>Hospitals</b> | City of Hamilton https://open.hamilton.ca/datasets/a5867b5375544ceb8f06544a5ed349a5_15/explore?location=43.243107%2C-79.843051%2C13.18 |
| <b>Fire stations</b>| City of Hamilton  https://open.hamilton.ca/datasets/dbb028cd6bcc4b218c607952b760fd04_5/explore?location=43.259500%2C-79.910650%2C11.81 |
| <b>Age by CT in 2016</b><br>| City of Hamilton https://data-spatialsolutions.opendata.arcgis.com/datasets/cdc66a4b09a147c39eeb747c15d5f9d8_4/explore?showTable=true |
| <b>Streets</b>| City of Hamilton https://open.hamilton.ca/datasets/f7af2fb9139444a0b3331f4663c16b15_14/explore?location=43.291554%2C-79.935150%2C11.18 |
| <b>Watercourse (rivers)</b> | City of Hamilton https://open.hamilton.ca/datasets/6b303eed313244a992b1fdf3935cc1dd_7/explore?location=43.259900%2C-79.934300%2C11.21 |
| <b>buildings</b>| City of Hamilton |
| <b>Soil Landscapes of Canada</b> | Soil Landscapes of Canada Working Group, 2011. Soil Landscapes of Canada version 3.2. Agriculture and Agri-Food Canada. |
| <b>Digital Elevation Model (DEM) - Provincial Tiled Dataset</b><br> | Ontario Mortality Data 2005- 2009, Ontario Geospatial Data Exchange (OGDE), Ministry of Natural Resources (OMNR) Ontario, Canada |
| <b>Digital surface model derived from imagery</b> | Ontario GeoHub https://geohub.lio.gov.on.ca/maps/mnrf::ontario-digital-surface-model-imagery-derived/explore?location=43.541814%2C-79.509764%2C7.68 |
| <b>Lithology</b> | https://www.geologyontario.mndm.gov.on.ca/mndmaccess/mndm_dir.asp?type=pub&id=MRD126-REV1 |

Table 3. eastQUAKEs Near You Data.
| <b>Data Layer</b> | <b>Data Source</b> |
| --- | --- |
| <b>Earthquakes in Canada </b>(1985-2019) | Government of Canada; Natural Resources | 
| <b>Significant Canadian earthquakes </b>(1600-2006) | GEOSCAN Geological Survey of Canada |
| <b>Census Subdivisions of Canada 2016</b> | The Living Atlas |
| <b>Population Centres 2018</b>| Derived from Administrative Boundaries in Canada |
 
## **Reference**   
 
Earthquake: https://www.thecanadianencyclopedia.ca/en/article/earthquake  

Earthquakes: Information & Facts:
https://www.redcross.ca/how-we-help/emergencies-and-disasters-in-canada/types-of-emergencies/earthquakes/earthquakes-information-facts  

EARTHQUAKES IN EASTERN CANADA: A THREAT THAT CAN BE
MITIGATED: 
http://www.geohazard.ggl.ulaval.ca/0_Keynotes/lamontagne.pdf 

Earthquakes and Plate Tectonics: 
https://openpress.usask.ca/physicalgeology/chapter/12-3-earthquakes-and-plate-tectonics-2/ 

Understanding intraplate earthquakes: 
https://blogs.egu.eu/divisions/gd/2020/07/08/intraplate_earthquake/ 

The 1929 Magnitude 7.2 "Grand Banks" earthquake and tsunami: 
https://earthquakescanada.nrcan.gc.ca/historic-historique/events/19291118-en.php 

Earthquake zones in Eastern Canada:
https://www.seismescanada.rncan.gc.ca/zones/eastcan-en.php 

Preparing for an earthquake: https://www.ready.gov/earthquakes#:~:text=Prepare%20Before%20an%20Earthquake&text=Make%20an%20Emergency%20Plan%3A%20Create,fire%20extinguisher%20and%20a%20whistle. 

DISASTER PREPAREDNESS AND SUSTAINABLE DISASTER RISK MANAGEMENT IN A CHANGING ENVIRONMENT: https://www.witpress.com/Secure/elibrary/papers/SDP20/SDP20036FU1.pdf 

Video and Audio references:
Stock footage credits: https://www.pexels.com/videos/ 
https://www.videvo.net/ 
National Geographic: https://www.youtube.com/watch?v=_r_nFT2m-Vg&t=39s
https://www.youtube.com/watch?v=e7ho6z32yyo
EarthScience Western Australia: https://www.youtube.com/watch?v=FjXb97qR5C8
 
Background music credits: https://www.bensound.com
 
Image credits to: 
https://doi.org/10.1016/j.pepi.2008.03.017 (Schematic cross-section of the subduction)
https://earthquakescanada.nrcan.gc.ca/historic-historique/events/19291118-en.php (Grand Banks earthquake images and newspaper)
https://www.seismescanada.rncan.gc.ca/zones/eastcan-en.php (Earthquake zones in Eastern Canada)
https://www.cgsentinel.com/uploads/images/2018/12/a31e02a5560bef97d5eee2ff136b4542.jpg (story map seismic background)
https://www.pexels.com/photo/building-construction-industry-house-11460993/ (Mike)
https://www.pexels.com/photo/people-water-building-bridge-5903489/ (Andrey Karpov)
https://www.pexels.com/photo/magnifying-glass-and-wind-rose-on-maps-7412095/ (Monstera)
https://www.pexels.com/photo/houses-near-trees-2079223/ (Emre Can Acer)
Halifax skyline (https://banffventureforum.com/home-2/halifax-skyline/)
Hamilton skyline (https://en.wikipedia.org/wiki/List_of_tallest_buildings_in_Hamilton,_Ontario)
Toronto skyline (https://unsplash.com/s/photos/toronto-skyline)
Ottawa skyline (https://www.istockphoto.com/photos/ottawa-skyline)
Montreal skyline (https://www.alamy.com/stock-photo/montreal-skyline.html)
Quebec skyline (https://www.shutterstock.com/image-photo/quebec-city-skyline-panorama-over-river-154975961)
Charlottetown skyline (https://www.myconsultant.ca/EN/A-Newcomers-Guide-to-Charlottetown)
Saint John skyline (https://www.paulsaulnier.com/2017/07/23/hometown-saint-john-new-brunswick/)
Moncton skyline (https://commons.wikimedia.org/wiki/File:Skyline_of_Moncton_in_2015_(cropped).jpg)
St.John’s skyline (https://www.123rf.com/photo_85839178_st-john-s-cityscape-with-a-port-capital-city-of-newfoundland-and-labrador-canada.html)
Earthquakes Canada reported a 5.2 magnitude earthquake hit near Shawville, Quebec image https://www.ctvnews.ca/canada/central-canada-quakes-a-closer-look-at-the-region-s-risk-of-tremors-1.1286076 
https://www.pexels.com/photo/first-aid-kit-on-gray-background-5673523/ (Roger Brown)
https://www.pexels.com/photo/photo-of-a-person-covering-her-head-with-her-sweater-6951520/ (cottonbro)
