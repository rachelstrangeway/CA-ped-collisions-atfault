# Pedestrian-Involved Traffic Collisions: Who's at Fault?

## Assessing the rate of pedestrian-involved collisions and the at-fault party in California from 2012-2021.

Poor pedestrian safety in the United States is a pervasive and worsening issue. In the past few decades, there has been an overall decrease in road fatalities due to improved vehicle safety design and seatbelt regulations. However, pedestrian fatalities have risen, and currently make up a disproportionate share of road fatalities in comparison to the mode share of walking vs driving both nationally and in California. 

placeholder image

There are many facets to improving pedestrian safety and minimizing the burden of injury or death on victims and their families. While much of the focus is rightfully on the need to prevent collisions from happening in the first place, or reducing their severity if they do happen, events that happen after the collision can also have last impacts on victims. Namely, the at fault determination of a collision can have material, emotional, and cultural impacts on 

### At Fault Determination - Why does this matter?

California is considered a comparative at fault state. This means that if two parties are involved in a collision and Party A is found to be 70% responsible while Party B is 30% responsible, Party B is still financially liable for 30% of overall damages. This liability share is determined in an insurance claim by a few different factors, including party and witness interviews, photo evidence, and any on-file police or individual report, which must include a Primary Collision Factor and cited party at fault. There are several implications of the at fault determination on a police report – it can determine if the collision will appear on your driver record, can cause insurance rates to increase, may be used as evidence in a personal injury lawsuit, and can be factored into an insurance adjuster’s liability determination. 

placeholder image

### Research Questions
The following analysis assesses the rate of pedestrian at fault determinations in an effort to understand geographic differences and disparities of this rate. The following research questions will be addressed:
* Comparing across city geographies, at what rate are pedestrians found at fault for fatal crashes?
* How might the pedestrian at-fault rate correlate with overall crash rates, population density, mode share, or walk score?
* How does the pedestrian at fault rate vary by census tract across key cities?

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
* SafeTREC Transporation Injury Mapping System (TIMS) (2012-2021)
* NHTSA Fatality Analysis Reporting System (FARS) (1994-2020)
* American Census Survey (2020 5-year estimate)
* National Household Travel Survey (NHTS) (2017)

The following analytical tools were performed in Python Jupyter Notebooks: 
* Cross tabulation
* Bivariate linear regression
* Hexgrid Choropleth Spatial Analysis

### Summary Data: Key Cities

According to this analysis, from 2012 to 2021 there were a total of 2,882 fatal and 7,996 severe pedestrian-involved crashes in cities listed.

"Pedestrian" was cited as the party at-fault on average **50% of the time**.

This is noteable, considering that in nearly all of these crashes, the pedestrian victim was likely the party to suffer serious injury or death. While pedestrians are not the main source of danger in roads, they experience disproportionate burden of blame of the collisions in which they are involved. 

The following charts show this data further broken down by city, party at fault, and crash severity. The chart on top shows fatal collisions while the chart on the bottom shows severe collisions. 

Image placeholder. 

Image placeholder. 

Here, there are some noteable patterns. First, we can see that in almost every city (except for Berkeley), Pedestrians (indicated by the grey bar) are found at fault at a rate higher than any other mode in pedestrian-involved collisions. In the case of the city of Thousand Oaks, while only 11 severe and fatal collisions occured from 2012-2021, pedestrians were found at fault for 100% of those crashes. 

There is also a difference in these rates when comparing fatal crashes to severe-injury crashes. As both of these charts use the same y-axis scale, we can see that pedestrians are found at fault at a lower rate on average for severe crashes as compared to fatal crashes. This could be due to a few factors. First, since crash severity is highly correlated to vehicle speed, it's possible that these crashes are occuring on lower speed roads, where there is likely less road space dedicated to cars, and more dedicated to alternative modes like transit, cycling, and walking. Alternatively, there is the more concerning fact that much of the information that police officers take into account when determining the at fault party comes from involved parties themselves. In the case where a pedestrian collision is fatal, the victim may not be able to advocate for themselves which would result in biased information from only the driving party. 

### Regression Analysis

In order to investigate the geographic variation across cities, linear regression analysis was performed on four independent variables: walk score, walk and transit mode share, population density, and overal pedestrian crash rate per capita. Walk score was chosen as a measure of qualitative "walkability" of a city. Walk and transit mode share was chosen to as a measure of pedestrian volume. Transit was included since many individuals taking transit walk the first or last mile of their trip. Population density was chosen as a measure of both pedestrian and intersection volume. And overall pedestrian crash rate was chosen as a measure of general pedestrian safety in a city. The regression analysis yielded the following results: 

Image placeholder. 

Image placeholder. 

Image placeholder. 

Image placeholder. 

Across the sample of 15 cities, pedestrian at-fault rate was found to be most highly correlated to city walk score (R squared = , p value = . At-fault rate was also highly correlated to walking + transit commute mode share and population density. The at-fault rate was found to have low correlation to overall pedestrian crash rate (R squared = ). This indicates that higher pedestrian volume and walkability could be correlated with better pedestrian infrastructure or a higher awareness of pedestrians which could influence how fault is determined in a crash. Interestingly, there doesn't appear to be a correlation between the at fault rate and overall pedestrian safety, indicated these two issues are not interdependent. 

### Spatial Analysis
Lastly, 




