# cycling_complaints_bw_swr

## Summary
The goal of this project is to process and analyze data collected by the SWR (Südwestrundfunk) in context of their [#besserRadfahren](https://www.swr.de/radfahren/besser-radfahren-im-suedwesten-106.html) campaign. The data was gathered by collecting complaints from cyclists in the south-west of Germany (Baden-Württemberg and Rheinland-Pfalz). The resulting dataset can be sccessed [here](https://www.govdata.de/web/guest/daten/-/details/besserradfahren-swr-umfrage) through _GovData.de_.
The pre-processing and short analysis focus on the state of Baden-Württemberg and in particular on it's capital city, Stuttgart.

The analysis is performed in R and presented in a R markdown format.

## Data Cleaning



## Insights
This serves as an overview of the results from the performed analysis. Short chapters display most notable insights accompanied by some context-providing commentary.

### Baden-Württemberg vs. Stuttgart
The first analysis focuses on the differences between Baden-Württemberg and Stuttgart in regard to the five main categories of complaints submitted by cyclists.

<p align="center">
  <img src="images/1_bw_vs_stuttgart.png" width="80%" />
</p>

We can observe that for both reagions the overwhelming cause of complaints with roughly 80% is _Verkehrsführung_, the layout of cycling roads. With Stuttgart being the capital city and containging high amounts of traffic while simultaniously having a relatively weak cycling infrastructure, it is expected to have a bigger problem with _Verkehrsführung_ than the state as a whole. The same circumstances also likely result in the higher amount of _Behinderung_, obstructions on the cycling roads.
On the other hand, _Zustand des Radwegs/der Straße_, the road conditions, seem to cause close to half as many problems in Stuttgart as in the state. However, this is likely because the cyclist in Stuttgart are forced to drive on roads intended for cars and these are mostly well maintained.
Further, the data seems to indicate that the situation regarding _Fahrradständer_, bike parking racks, in Stuttgart is very good and significantly better than in the state.

### Inner City Districts of Stuttgart
Inspecting the five innter city districts of Stuttgart, we observe that the most problematic district are the city center and the south. While some aspects, such as the road layout and the road conditions are almost identical, there are significant differences in the other categories. Most notably, in the amount of obstructions where the situation in the city center is more than twice as bad as in the south. On the other hand, _Schilder/Markierung/Beleuchtung_, the road signs/markings/illumination seems to be, by far, the worst the the south of the city.

<p align="center">
  <img src="images/2_stuttgart_inner_dist.png" width="80%" />
</p>
 
### Progression of Complaints over Time in Stuttgart

<p align="center">
  <img src="images/3_stuttgart_trend.png" width="80%" />
</p>

Observing the weekly publications by total counts, we get a more precise picture of the decrease in publications towards the weekend. While the counts don't drop below the 500 mark during the regular work week, they remain between low to mid 300s on the weekend.

### Five Largest Cities in Baden-Württemberg

To get a sense of how these publications came to be, we need to inspect their authorship. Given the large number of journalists working for CNN, we don't want to look at every single one individually but group them together. In this context it seems of particular interest to examine the spirit of collaboration in a journalistic environment. Therefore, we make the distinction between a single person worked on an article and a group of people contributing to its content. Additionally, articles which don't contain a reference and where the author is therefore unknown are also included.

<p align="center">
  <img src="images/4_bw_top5.png" width="80%" />
</p>

Inspecting the chart, we observe a relationship of almost 2 to 1 in favor of individual work. At this point, jumping to the conclusion that CNN journalists are not particularly fond of each other would likely, on its own, make for some flashy headlines that would definitely find their target audience... A more objective interpretation of these insights, however, is that, for most day-to-day news reports, one journalist is enough.





### Monthly Close-Up
While the analysis described so far focused on data collected over the whole year, we can also inspect each month individually.
This is exemplified on the month of January.

<p align="center">
  <img src="images/pub_month.png" width="40%" />
</p>

In this chart we can see the publication counts for each day of the month. An average range for this month is computed by utilizing the mean value and the standard deviation. Days on which the number of published articles lays within this range are displayed in blue while positive outliers are green and the negative red.
Knowing that the first day of 2021 was a Friday we infer that the two days marked as red, the 10th and the 23rd were a Sunday and Saturday, respectively. Taking the insights from previous analysis of individual weekdays into account, we know that this observation is nothing out of the ordinary.
