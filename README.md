# cycling_complaints_bw_swr

## Summary
The goal of this project is to process and analyze data collected by the SWR (Südwestrundfunk) in context of their [#besserRadfahren](https://www.swr.de/radfahren/besser-radfahren-im-suedwesten-106.html) campaign. The data was gathered by collecting complaints from cyclists in the south-west of Germany (Baden-Württemberg and Rheinland-Pfalz). The resulting dataset can be sccessed [here](https://www.govdata.de/web/guest/daten/-/details/besserradfahren-swr-umfrage) through _GovData.de_.
The pre-processing and short analysis focus on the state of Baden-Württemberg and in particular on it's capital city, Stuttgart.

The analysis is performed in R and presented in a R markdown format.

## Data Cleaning



## Insights
This serves as an overview of the results from the performed analysis. Short chapters display most notable insights accompanied by some context-providing commentary.

### Baden-Württemberg vs. Stuttgart
Having an initial objective impression of the data provides us not only with valuable insights but also allows us to develop intuition as to where we want to take the analysis. To accomplish this first step, we need to inspect the progression of publications throughout the whole year.

<p align="center">
  <img src="images/1_bw_vs_stuttgart.png" width="80%" />
</p>

Here we observe a significant degree of fluctuation in the number of publications. The yellow trend line is used to visualize this fluctuation further by performing polynomial regression on the data. Despite this fluctuation, we can observe a steady growth in productivity throughout the year as visualized by the green trend line utilizing linear regression. Inspecting this line, we can observe a substantial increase of 53.60% at the end of the year. When this analysis was originally performed using only data from January to November the prediction for the end of the year amounted to over 60%. The strong drop off in publications in December (especially in the second half of the month, which is presumably correlated with the holiday season) resulted in a downwards adjustment of the overall positive trend by around 10%.

### Inner City Districts of Stuttgart
Viewing the reporting on news as a recurring "workweek" event throughout the year while also keeping the previously observed fluctuation in mind, it becomes of interest to inspect the contribution of individual weekdays to the overall picture. Therefore, we condense the information from the whole year into a one week representation.

<p align="center">
  <img src="images/2_stuttgart_inner_dist.png" width="80%" />
</p>
 
Here, we make the most notable observation when inspecting the regular workdays and the weekend. Monday through Friday display a slightly variating mean of around 10 to 11 and an identical median of 10. When moving to the weekend, we observe a significant decrease to a mean of 6 to 7 and a median of 7 for Saturday and 6 for Sunday as well as an overall decrease in publications. Additionally, we see an overall low occurrence of outliers which is, however, more present on the weekend.

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
