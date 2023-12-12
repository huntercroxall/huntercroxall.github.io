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
First, go to the [OpenFDA website](https://open.fda.gov/apis/authentication/). From there, click on the blue button that says "Get API Key". Follow the steps from there to receive the API key. Make sure to never share your API key online by placing it in a gitignore file and accessing you API key file remotely. API keys should never be shared in public. 

Now that you have an API key, you can access a huge variety of data gathered by the FDA! This post will specifically examine how to collect data on food recall enforcements, but the [OpenFDA website](https://open.fda.gov/apis/) has many useful guides to help you access the entirety of their public datasets. 

---

## Step 3: Use the API Key to Request Data

