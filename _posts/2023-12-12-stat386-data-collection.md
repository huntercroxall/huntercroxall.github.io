---
layout: post
title:  "API Data Collection Methods for Stat 386 Project"
author: Hunter Croxall
description: A short blog post describing the process for using the OpenFDA API key.
image: "/assets/images/braden-jarvis-prSogOoFmkw-unsplash.jpeg"
---

## Introduction:
For my Stat 386 project, I chose to use an API Key to access the OpenFDA database. The FDA, or Food and Drug Administration, of the United
States Government records data on a variety of foods, drugs, and devices. The OpenFDA database allows the public to access this data and
complete analysis on a variety of aspects of this data. For the sake of this blog post, I decided to gather data regarding recalls of various
foods. This blog post will describe the process used to gather the data using the OpenFDA API.

---

## Step 1: Install Necessary Libraries
For this project, you need four libraries: 
**pandas**, to convert the data gathered via API key into a data frame 
**requests**, to call in the data from the OpenFDA API source
**seaborn**, to design data visualizations
**matplotlib.pyplot**, also to help with the creation of data visualizations

Make sure you install all four of these packages, then you can easily import them into the code using the code below:
```
import pandas as pd
import requests
import seaborn as sns
import matplotlib.pyplot as plt
```

---

## Step 2: Get an API Key from OpenFDA to Access Data

