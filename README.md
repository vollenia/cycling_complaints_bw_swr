# cycling_complaints_bw_swr

## 1. Summary
The goal of this project is to process and analyze data collected by the SWR (Südwestrundfunk) in context of their [#besserRadfahren](https://www.swr.de/radfahren/besser-radfahren-im-suedwesten-106.html) campaign. The data was gathered by collecting complaints from cyclists in the south-west of Germany (Baden-Württemberg and Rheinland-Pfalz). The resulting dataset can be accessed [here](https://www.govdata.de/web/guest/daten/-/details/besserradfahren-swr-umfrage) through _GovData.de_.
The pre-processing and short analysis focus on the state of Baden-Württemberg and in particular on its capital city, Stuttgart.

The analysis is performed in R and presented in an R markdown format.

## 2. Data Cleaning
To achieve the desired shape and quality of data the described dataset needed to undergo several data cleaning steps. All of these steps are included and documented in the R markdown file. What follows is a short summary of the most interesting steps taken.

Arguably, the most important challenge in this context was the extraction of state, district and city names as well as zip codes for each entry in the original dataset where all of them were part of a single text string. Therefore, this text string needed to be split in a multi-step process.

While this process was largely a success it brought some additional challenges with it. One of those challenges was that e.g. the state names resembled the same names in different languages. These includes variations of Baden-Württemberg in Spanisch (_Baden-Wurtemberg_), French (_Bade-Wurtemberg_) and Japanese (_バーデン＝ヴュルテンベルク州_), among others.

Other steps included common data cleaning such as the removal of zeroes and outliers. This also included instances where the previously mentioned split didn't deliver the desired results due to missing values in the original dataset. 

## 3. Insights
This serves as an overview of the results from the performed analysis. Short chapters display most notable insights accompanied by some context-providing commentary.

### 3.1 Stuttgart vs. Baden-Württemberg
The first analysis focuses on the differences between Baden-Württemberg and Stuttgart in regard to the five main categories of complaints submitted by cyclists.

<p align="center">
  <img src="images/1_stuttgart_vs_bw.png" width="80%" />
</p>

We can observe that for both regions the overwhelming cause of complaints with roughly 80% is _Verkehrsführung_, the layout of cycling roads. With Stuttgart being the capital city and containing high amounts of traffic while simultaneously having a relatively weak cycling infrastructure, it is expected to have a bigger problem with the layout of cycling roads than the state as a whole. The same circumstances also likely result in the higher amount of _Behinderung_, obstructions on the cycling roads.
On the other hand, _Zustand des Radwegs/der Straße_, the road conditions, seem to cause close to half as many problems in Stuttgart as in the state. However, this is likely because the cyclist in Stuttgart are forced to drive on roads intended for cars and these are mostly well maintained.
Further, the data seems to indicate that the situation regarding _Fahrradständer_, bike parking racks, in Stuttgart is very good and significantly better than in the state.

### 3.2 Inner City Districts of Stuttgart
Inspecting the five inner city districts of Stuttgart, we observe that the most problematic districts are the city center and the south. While some aspects, such as the road layout and the road conditions are almost identical, there are significant differences in the other categories. Most notably, in the amount of obstructions where the situation in the city center is more than twice as bad as in the south. On the other hand, _Schilder/Markierung/Beleuchtung_, the road signs/markings/illumination seems to be, by far, the worst in the south of the city.

<p align="center">
  <img src="images/2_stuttgart_inner_dist.png" width="80%" />
</p>
 
### 3.3 Progression of Complaints over Time in Stuttgart
Viewing the timeline of complaints submitted in Stuttgart, we observe an overarching trend throughout almost all categories. There is a constant increase in contributions from cyclists that culminates in a peak at around mid March and then drops off before reaching plateau at the beginning of April. The only outlier to this behavior are the obstructions on the roads which display a constant downward trend.
Disregarding the outlier and speculating about the reasons behind this overarching trend, it would be wishful thinking and very unlikely that all of the reported problems were resolved in a matter of weeks. Likely, the majority of the problematic spots across the city have just been mapped by the cyclists and only a handful of those problems has been resolved.

<p align="center">
  <img src="images/3_stuttgart_trend.png" width="80%" />
</p>

### 3.4 Five Largest Cities in Baden-Württemberg

To conclude this short analysis, we look at the top five cities with the highest population in Baden-Württemberg. Doing so, allows us to also compare Stuttgart with 4 other cities.

<p align="center">
  <img src="images/4_bw_top5.png" width="80%" />
</p>

The comparison reveals once again that Stuttgart has relatively good road conditions and that the problem of a bad cycling road layout affects the city to a similar extent as other cities. Further, the road signs, markings and illumination in Stuttgart seem to be average while problems with bike parking racks seem almost non-existent. Most surprisingly, out of the five largest cities Stuttgart ranks the second best in regard to obstructions on cycling roads while being the largest and having almost four times the population of the smallest city on the list and twice its density.
