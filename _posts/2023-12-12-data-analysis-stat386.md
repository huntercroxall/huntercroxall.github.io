---
layout: post
title:  "Data Analysis for Stat 386 Project"
author: Hunter Croxall
description: Interesting findings from the OpenFDA API Dataset
image: "/assets/images/kyle-cottrell-wIscdBkwnrM-unsplash.jpeg"
---

## Introduction
For my Stat 386 project at BYU, I decided to analyze a set of data collected from the OpenFDA API. I specifically analyzed egg-related recall events. This blog contains a series of visualizations that I created while exploring this data. I also describe how I created each of these visualizations using pandas, seaborn, and matplotlib.plotly to produce each of these graphs. 


## Visualization 1: Bar Chart of Classification of Recall
For my first visualization, I want to see how common each type of recall was. The recall classification calls recalls of high risk to the public as "Class 1", while calling less serious or dangerous recalls as "Class 3". Interestingly, this graph shows that the vast majority of egg-related recalls are in the "Class 1" category. When I queried the API for data not based on reason for recall, I found that the difference between the number of "Class 1" and "Class 3" recalls is much smaller.
![Look at this wonderful graph!](/assets/images/count_by_classification.png "Count By Classification")


