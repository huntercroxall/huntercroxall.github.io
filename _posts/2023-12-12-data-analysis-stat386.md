---
layout: post
title:  "Data Analysis of Egg-Related Recalls in the US by the FDA (2012-2023)"
author: Hunter Croxall
description: Interesting findings from the OpenFDA API Dataset regarding egg-allergen recalls
image: "/assets/images/kyle-cottrell-wIscdBkwnrM-unsplash.jpeg"
---

## Introduction
For my Stat 386 project at BYU, I decided to analyze a set of data collected from the OpenFDA API. I specifically analyzed egg-related recall events. My motivation for selecting this data was ease of access and curiousity about the various data the government collects. I don't honestly have a deep love for examining egg-related FDA recall events, but I do like to understand the sort of data the government collects and stores. I find it intriguing that an OpenFDA API has been created to give the public access to information regarding the actions of the FDA. I have learned more about the world of government regulation through this project. This blog contains a series of visualizations that I created while exploring this data. I also describe how I created each of these visualizations using pandas, seaborn, and matplotlib.plotly to produce each of these graphs. By doing this, I hope that you will gain insights about the recall system implemented by the United States, and enjoy learning about the programming used to produce such an analysis. 

---

## Visualization 1: Pie Chart of Classification of Recall
For my first visualization, I wanted to see how common each type of recall was. The recall classification calls recalls of high risk to the public as "Class 1", while calling less serious or dangerous recalls as "Class 3". Interestingly, this graph shows that the vast majority of egg-related recalls are in the "Class 1" category.

![Look at this wonderful graph!](/assets/images/pie_chart_classification.png "Proportion By Classification")

---

## Visualization 2: Bar Chart of State Where Recall Occurred
For my second visualization, I wanted to see where the majority of the the recalls occurred. Unsuprisingly, due to its massive population, California took first place with the most. However, I was suprised to see that Washington is second in terms of egg-related recall events. I also noticed that states with higher populations tended to have more recall events than other states. This of course makes sense since more people will inevitably mean more product production and likelihood of recall events occurring.

![Look at this wonderful graph!](/assets/images/count_by_state.png "Count By State")

---

## Visualization 3: Line Chart of Recall Events by Year
For my third visualization, I wanted to see which year has seen the most recall events since 2012. Interestingly, a major spike occurred in 2017 for reasons I don't know. I also noticed that after the increase in recalls after 2017, the number of recall events remained substantially higher than the years prior to 2017. 

![Look at this wonderful graph!](/assets/images/line_graph.png "Line Graph by Year")

---

## Visualization 4: Scatterplot Comparing When A Report was Made and When the Report was Terminated
For my fourth visualization, I wanted to see how long a recall event is. I created this scatter plot to see if most events resolve quickly or extend further into the future. I did this by graphing the date of the report against the date when the report was terminated. This allowed me to see that most recall events only last for a short time, while a small number of them remain in force for more than 6 months. Although this graph does not provide great insights for every individual data point, the aggregate points make a clear point that recall events do not usually last very long. 

![Look at this wonderful graph!](/assets/images/scatterplot_datetimes.png "Scatterplot by Date")

---

## Visualization 5: Boxplots Measuring Distribution of Month of Recall Report and Separated into Three Plots Based on Classification
For my fifth visualization, I wanted to examine two things. First, I wanted to see if the number of recall reports changes at different times of a given year. I also wanted to see if certain types of recalls were more likely to occur at different times of the year. By creating this graph, I was able to see some intriguing trends. No Class 3 classification recalls have occurred in November or December since 2012. I also noticed that Class 1 recalls occur fairly evenly over the duration of the year, but Class 2 recalls occur more often in the beginning year. I have no idea why this skew exists in the data since I feel that recalls occur regardless of season, but this data seems to provide evidence to the contrary.

![Look at this wonderful graph!](/assets/images/boxplot_month.png "Boxplot by Class")

---

## Visualization 6: Multiple Bar Chart Measuring Count of Recall Events Separated by Month and Classification
For my sixth visualization, I wanted to delve further into what I saw in my fifth visualization. I did this by measuring by the count of recall events by month separated by classification. I found that a huge number of Class 1 recall events have occurred in May, and there happens to be more recall events earlier in the year rather than later in the year for all three Class types. The skew noticed in my fifth visualization again appeared in the Class 2 recall event portion of the graph, but now I could clearly see that most Class 2 recall events take place in March and April and almost none occur between October and December. 

![Look at this wonderful graph!](/assets/images/multiple_bar_chart_month.png "Multi-Bar by Class and Month")

---

## Summary of Findings
**Visualization 1**: In visualization 1, I found that over 70% of recall events are classified as Class 1. This means that a majority of recalls are made in cases when the product can put consumers at a high risk of harm. This suprised me, since I expected to see more low-risk recalls since those seem more likely to occur. However, it makes sense that a production mistake is more likely to be recalled if the risk to consumers is life-threatening.  
**Visualization 2**: In visualization 2, I learned that the most recalls occur in the state of California, with Washington and Texas in second and third respectively. I thought that the number of recalls in a state would correlate with the population of the state, but this was not proven entirely true because Washington surpassed several states that have millions more people. However, with the few exceptions of Washington and Iowa, the number of recalls did relate to the population of the state.  
**Visualization 3**: In visualization 3, I completed a line chart of recall events over the past 10 years. Interestingly, I found that 2017 saw the most recall events by a significant margin in comparison to the other years. I also found that following 2017, the number of recall events remained fairly high in comparison to prior to the 2017 spike.  
**Visualization 4**: In visualization 4, I created a scatterplot to measure the difference in time between when a recall event report was created and when the recall event was terminated and no longer in effect. This revealed that most recall events take less than 6 months to resolve with very few outliers. I also noticed that the length of recalls has become shorter as time has passed from 2012 to 2023.  
**Visualization 5**: In visualization 5, I found through boxplots that recall events tend to happen earlier in the year. I found that Class 2 recall events tend to occur earlier in the year than Class 1 and Class 3 recalls. I also found that Class 1 recalls spread out fairly evenly over the duration of a year, with a slight skew towards the beginning of the year.  
**Visualization 6**: In visualization 6, I further examined the things I learned in visualization 5 to find which months experienced the most recall events based on class. I learned that Class 1 events occur most often in May, and Class 2 events occur most often in March and April. I also found that the limited number of Class 3 events had resulted in the intriguing boxplot created in visualization 5.  


## Conclusion
In conclusion, I learned a number of interesting things about egg-related recall events. There is room for in-depth analysis of why more recall events occur in the spring, why more Class 1 events are created rather than less life-threatening recalls, and why the number of recalls has drastically changed during various years like 2017. By completing an exploratory data analysis on this data, I was able to learn about egg-related FDA recall events in an insightful way. Just reading the rows of the data would not help anyone reach the findings I came to. By using exploratory data analysis, I was able to learn so much more about this interesting dataset provided by the OpenFDA API.


---
---
#### Important note: 
Here is the link to my github repository where my data and code is stored if you would like to see the coding process used and the data collected. [Hunter Croxall Github](https://github.com/huntercroxall/s386Fall2023-project)
