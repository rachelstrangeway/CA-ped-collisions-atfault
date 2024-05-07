# Pedestrian-Involved Traffic Collisions: Who's at Fault?

## Assessing the rate of pedestrian-involved collisions and the at-fault party in California from 2012-2021.

Poor pedestrian safety in the United States is a pervasive and worsening issue. In the past few decades, there has been an overall decrease in road fatalities due to improved vehicle safety design and seatbelt regulations. However, pedestrian fatalities have risen, and currently make up a disproportionate share of road fatalities with respect to mode share both nationally and in California. 

<p align="center">
<img width="334" alt="US Traffic Fatalities by Mode" src="https://github.com/rachelstrangeway/CA-ped-collisions-atfault/assets/157441987/63a42916-2fea-4dff-b8bf-de2b6404102e">
</p>

*<p align="center">
FARS Recorded Traffic Fatalities (NHTSA, 2020)*
</p>

There are many facets to improving pedestrian safety and minimizing the burden of injury or death on victims and their families. While much of the focus is rightfully on the need to prevent collisions from happening in the first place, or reducing their severity if they do happen, events that happen after the collision can also have lasting impacts on victims. Namely, the at fault determination of a collision can have material, emotional, and cultural impacts on individuals and communities.

### At Fault Determination - Why does this matter?

California is considered a [comparative at fault](https://www.investopedia.com/terms/c/comparative-negligence.asp#:~:text=Comparative%20negligence%20states%20that%20when,and%20pay%20insurance%20claims%20accordingly.) state. This means that if two parties are involved in a collision and Party A is found to be 70% responsible while Party B is 30% responsible, Party B is still financially liable for 30% of overall damages. This liability share is determined in an insurance claim by a few different factors, including party and witness interviews, photo evidence, and any on-file police or individual reports, which must include a Primary Collision Factor and cited party at fault. There are several implications of the at fault determination on a police report – it can determine if the collision will appear on your driver record, can cause insurance rates to increase, may be used as evidence in a personal injury lawsuit, and can be factored into an insurance adjuster’s liability determination. 

<p align="center">
<img width="193" alt="Primary Collision Factor" src="https://github.com/rachelstrangeway/CA-ped-collisions-atfault/assets/157441987/09a1a69d-42d0-4b39-9e61-62d4e6da56eb">
</p>

*<p align="center">
Primary Collision Factor Field in CHP Form 555 (California Highway Patrol, 2012)*
</p>

### Research Questions
The following analysis assesses the rate of pedestrian at fault determinations in an effort to understand geographic differences and disparities of this rate. The following research questions will be addressed:
* Comparing across city geographies, at what rate are pedestrians found at fault for fatal and severe crashes?
* How might the pedestrian at-fault rate correlate with overall crash rates, population density, mode share, or walk score?
* How does the pedestrian at fault rate spatially across key cities?

### Methodology

In this report, the "pedestrian at fault rate" is defined as follows:

***<p align="center">
Pedestrian at Fault Rate***
</p>
  
*<p align="center">
The number of pedestrian-involved crashes in which the pedestrian is cited as at-fault divided by the number of pedestrian-involved severe and fatal crashes*
</p>

In this analysis, only severe and fatal collisions were chosen since these types of collisions have the lowest rates of underreporting as well as the greatest burden on victims and communities. The key cities analyzed are a combination of the most populous cities in California, as well as those with high or low rates of pedestrian collisions per capita. 

The following datasets were used throughout this report:
* [SafeTREC Transporation Injury Mapping System (TIMS) (2012-2021)](https://tims.berkeley.edu/tools/gismap/)
* [NHTSA Fatality Analysis Reporting System (FARS) (1994-2020)](https://www.nhtsa.gov/research-data/fatality-analysis-reporting-system-fars)
* [American Community Survey (2020 5-year estimate)](https://data.census.gov/)

The following analytical tools were performed in Python Jupyter Notebooks: 
* Cross tabulation
* Bivariate linear regression
* Hexgrid Choropleth Spatial Analysis

### Summary Data: Key Cities

According to this analysis, from 2012 to 2021 there were a total of 2,882 fatal and 7,996 severe pedestrian-involved crashes in cities listed.

"Pedestrian" was cited as the party at-fault on average **50% of the time**.

This is noteable, considering that in nearly all of these crashes, the pedestrian victim was likely the party to suffer serious injury or death. While pedestrians are not the main source of danger in roads, they experience disproportionate burden of blame for the collisions in which they are involved. 

The following charts show this data further broken down by city, party at fault, and crash severity:

<p align="center">
<img width="2000" alt="Fatal Collision at Fault Rate by City" src="https://github.com/rachelstrangeway/CA-ped-collisions-atfault/assets/157441987/ce95e70b-80b1-46eb-bb22-374d9603ea26">
</p>

<p align="center">
<img width="2000" alt="Severe Collision at Fault Rate by City" src="https://github.com/rachelstrangeway/CA-ped-collisions-atfault/assets/157441987/8bdd4d54-4a28-41dd-b87b-199d4cedece1">
</p>

*<p align="center">
Top: Fatal Collisions by city, party at fault, and severity. Bottom: Severe Collisions by city, party at fault, and severity. (SWITRS TIMS 2012-2021, author's own calculations)*
</p>

Here, there are some noteable patterns. First, we can see that in almost every city (except for Berkeley), Pedestrians (indicated by the grey bar) are found at fault at a rate higher than any other mode in pedestrian-involved collisions. In the case of the city of Thousand Oaks, while only 11 severe and fatal collisions occured from 2012-2021, pedestrians were found at fault for 100% of those crashes. 

There is also a difference in these rates when comparing fatal crashes to severe-injury crashes. As both of these charts use the same y-axis scale, we can see that pedestrians are found at fault at a lower rate on average for severe crashes as compared to fatal crashes. This could be due to a few factors. First, since crash severity is highly correlated to vehicle speed, it's possible that these crashes are occuring on lower speed roads, where there is likely less road space dedicated to cars, and more dedicated to alternative modes like transit, cycling, and walking. Therefore, pedestrians may have safer infrastructure such as signalized crossings, or drivers may be more accumstomed to pedestrians having the right-of-way. Alternatively, there is the more concerning fact that much of the information that police officers take into account when determining the at fault party comes from involved parties themselves. In the case where a pedestrian collision is fatal, the victim may not be able to advocate for themselves which would result in biased information from only the driving party. 

### Regression Analysis

In order to investigate the geographic variation across cities further, linear regression analysis was performed on four independent variables: walk score, walk and transit mode share, population density, and overal pedestrian crash rate per capita. Walk score was chosen as a measure of qualitative "walkability" of a city. Walk and transit mode share was chosen to as a measure of pedestrian volume. Transit was included since many individuals taking transit walk the first or last mile of their trip. Population density was chosen as a measure of both pedestrian and intersection volume. And overall pedestrian crash rate was chosen as a measure of general pedestrian safety in a city. The regression analysis yielded the following results: 

<img width="400" alt="Walk Score At Fault Rate Regression" src="https://github.com/rachelstrangeway/CA-ped-collisions-atfault/assets/157441987/1897204e-6df1-43b3-ab3e-485d71969570">
<img width="400" alt="Mode Share At Fault Rate Regression" src="https://github.com/rachelstrangeway/CA-ped-collisions-atfault/assets/157441987/d2e934a3-c048-4d23-8c36-9c866d1f8ca5">
<img width="400" alt="Population Density At Fault Rate Regression" src="https://github.com/rachelstrangeway/CA-ped-collisions-atfault/assets/157441987/4fa3d796-c599-487d-8a45-ae8d5f53eefd">
<img width="400" alt="Crash Rate At Fault Rate Regression" src="https://github.com/rachelstrangeway/CA-ped-collisions-atfault/assets/157441987/5f383c3c-0f58-4e3b-963f-b132327f7471">

*<p align="center">
Top left: Walk Score and At Fault Rate Regression. Top right: Mode Share and At Fault Rate Regression. Bottom left: Population Density and At Fault Rate Regression. Bottom right: Crash Rate and At Fault Rate Regression. (SWITRS TIMS 2012-2021, author's own calculations)*
</p>

Across the sample of 15 cities, pedestrian at-fault rate was found to be most highly correlated to city walk score (R<sup>2</sup> = 0.616, p value = 0.001). At-fault rate was also highly correlated to walking + transit commute mode share (R<sup>2</sup> = 0.567, p value = 0.001). There was slightly lower correlation between at fault rates and  population density (R<sup>2</sup> = 0.385, p value = 0.014 ). The at-fault rate was found to have the lowest correlation to overall pedestrian crash rate (R<sup>2</sup> 0.138= , p value = 0.174). This indicates that higher pedestrian volume and walkability could be correlated with better pedestrian infrastructure or a higher awareness of pedestrians which could influence how fault is determined in a crash. Interestingly, there doesn't appear to be a correlation between the at fault rate and overall pedestrian safety, indicated these two issues are necessarily associated with eachother. 

### Spatial Analysis
Lastly, major metropolitan areas were spatially analyzed in order to indentify locations within the cities with the highest number of pedestrian-at-fault collisions. The results on of the hexbin choropleth mapping for Los Angeles and the key cities in the Bay Area are shown below.

<img width="400" alt="At Fault Rate Hexbins Los Angeles" src="https://github.com/rachelstrangeway/CA-ped-collisions-atfault/assets/157441987/80a507b0-df39-41cf-bf09-8b88e03d1f8d">
<img width="400" alt="At Fault Rate Hexbins Bay Area" src="https://github.com/rachelstrangeway/CA-ped-collisions-atfault/assets/157441987/bd22e7a2-60d9-4df0-9175-bbe757fae53a">

*<p align="center">
Left: Pedestrian At Fault Collisions by Hexbins in Los Angeles. Right: Pedestrian At Fault Collisions by Hexbins in Los Angeles. (SWITRS TIMS 2012-2021, author's own calculations)*
</p>

These maps show that the highest number of pedestrian at fault collisions tend to cluster around downtown areas. In Los Angeles, Downtown and South LA have the highest rates of pedestrian at fault collisions. In the Bay Area, the highest rates are in Downtown San Francisco, but there are other less extreme increases in these collisions in West and East Oakland as well as Downtown San Jose. Knowing the locations where pedestrian-at-fault collisions are most clustered can help guide planners and law enforcement in order to understand why these disparities are occuring. 

### Conclusion

While the pedestrian at-fault rate of a city is not directly correlated to overall road safety for pedestrians, there are still significant financial and emotional impacts on individuals and families when pedestrians are cited as at-fault for severe and fatal collisions. Both walk score and walking and transit mode share were highly correlated, but these might be proxy variables for higher pedestrian volume and frequent, high quality signalized crossings, which could reduce [“windshield bias”](https://usa.streetsblog.org/2023/11/17/world-day-of-remembrance-lets-banish-windshield-bias-and-talk-about-car-crashes) and minimize uncertainty about pedestrian right of way at intersections. 

There were several limitations to this report, including the relatively small dataset size, police report coding inaccuracies, and underreporting of collisions, which should be relatively small for fatal and severe crashes, but could still exist. Further research would be needed to understand how police training and infrastructure type and density further correlate with the pedestrian at fault rate. Understanding these relationships can help planners and police departments to make informed decisions about road design, traffic safety enforcement, and driving bias. 



