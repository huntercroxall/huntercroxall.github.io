---
layout: post
title:  "Data Analysis for Stat 386 Project"
author: Hunter Croxall
description: Interesting findings from the OpenFDA API Dataset
image: "/assets/images/kyle-cottrell-wIscdBkwnrM-unsplash.jpeg"
---

## Introduction
For my Stat 386 project at BYU, I decided to analyze a set of data collected from the OpenFDA API. I specifically analyzed egg-related recall events. My motivation for selecting this data is ease of access and curiousity about the various data the government collects. I don't honestly have a deep love for examining egg-related FDA recall events, but I do like to understand the sort of data the government collects and stores. I find it intriguing that an OpenFDA API has been created to give the public access to information regarding the actions of the FDA. I have learned more about the world of government regulation through this project. This blog contains a series of visualizations that I created while exploring this data. I also describe how I created each of these visualizations using pandas, seaborn, and matplotlib.plotly to produce each of these graphs. By doing this, I hope that you will gain insights about the recall system implemented by the United States, and enjoy learning about the programming used to produce such an analysis. 


## Visualization 1: Pie Chart of Classification of Recall
For my first visualization, I wanted to see how common each type of recall was. The recall classification calls recalls of high risk to the public as "Class 1", while calling less serious or dangerous recalls as "Class 3". Interestingly, this graph shows that the vast majority of egg-related recalls are in the "Class 1" category.

![Look at this wonderful graph!](/assets/images/pie_chart_classification.png "Proportion By Classification")


## Visualization 2: Bar Chart of State Where Recall Occurred
For my second visualization, I wanted to see where the majority of the the recalls occurred. Unsuprisingly, due to its massive population, California took first place with the most. However, I was suprised to see that Washington is second in terms of egg-related recall events. I also noticed that states with higher populations tended to have more recall events than other states. This of course makes sense since more people will inevitably mean more product production and likelihood of recall events occurring.

![Look at this wonderful graph!](/assets/images/count_by_state.png "Count By State")


## Visualization 3: Line Chart of Recall Events by Year
For my third visualization, I wanted to see which year has seen the most recall events since 2012. Interestingly, a major spike occurred in 2017 for reasons I don't know. I also noticed that after the increase in recalls after 2017, the number of recall events remained substantially higher than the years prior to 2017. 

![Look at this wonderful graph!](/assets/images/line_graph.png "Line Graph by Year")


## Visualization 4: Scatterplot Comparing When A Report was Made and When the Report was Terminated
For my fourth visualization, I wanted to see how long a recall event is. I created this scatter plot to see if most events resolve quickly or extend further into the future. I did this by graphing the date of the report against the date when the report was terminated. This allowed me to see that most recall events only last for a short time, while a small number of them remain in force for more than 6 months. Although this graph does not provide great insights for every individual data point, the aggregate points make a clear point that recall events do not usually last very long. 


