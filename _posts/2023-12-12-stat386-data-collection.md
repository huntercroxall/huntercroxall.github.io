---
layout: post
title:  "Collection of Data on Egg-Related Recall Events by the FDA (2012-2023): A Stat 386 Project"
author: Hunter Croxall
description: A short blog post describing the process for using the OpenFDA API key.
image: "/assets/images/braden-jarvis-prSogOoFmkw-unsplash.jpeg"
---
---

## Introduction and Motivation
For my Stat 386 project, I chose to use an API Key to access the OpenFDA database. The FDA, or Food and Drug Administration, of the United
States Government records data on a variety of foods, drugs, and devices. The OpenFDA database allows the public to access this data and
complete analysis on a variety of aspects of this data. For the sake of this blog post, I decided to gather data regarding recalls of various foods. This blog post will describe the process used to gather the data using the OpenFDA API. My motivation for selecting this data was ease of access and curiousity about the various data the government collects. I find it intriguing that an OpenFDA API has been created to give the public access to information regarding the actions of the FDA. I have learned more about the world of government regulation through this project. 

---

## Step 1: Install Necessary Libraries
For this project, you need four libraries: 
**pandas**, to convert the data gathered via API key into a data frame 
**requests**, to call in the data from the OpenFDA API source

Make sure you install both of these packages, then you can easily import them into the code using the code below:
```
import pandas as pd
import requests
```

---

## Step 2: Get an API Key from OpenFDA to Access Data
First, go to the [OpenFDA website](https://open.fda.gov/apis/authentication/). From there, click on the blue button that says "Get API Key". Follow the steps from there to receive the API key. Make sure to never share your API key online by placing it in a gitignore file and accessing you API key file remotely. API keys should never be shared in public. 

Now that you have an API key, you can access a huge variety of data gathered by the FDA! This post will specifically examine how to collect data on food recall enforcements, but the [OpenFDA website](https://open.fda.gov/apis/) has many useful guides to help you access the entirety of their public datasets. 

---

## Step 3: Use the API Key to Request Data
In ored to access the data, three parts of the request must be explicitly stated:
1. Headers: This tells the API what type of content you want to gather and how you will gather it (which is usually your API Key)
2. Parameters: These tell the query the keywords you want to search for and the number of data points you would like to collect that match the given keyword.
3. Endpoint: This informs the query of where in the API it needs to search for the provided data.

Here is an example of these three parts coming together to make a query on the API:
```
endpoint = "https://api.fda.gov/food/enforcement.json"

params = {
    'search':'reason_for_recall:"egg"',
    'limit': 500
}

headers = {
    'Content-Type': 'application/json',
    'api_key': api_key
}

response = requests.get(endpoint, params=params, headers=headers)
```
As you can see, you can change the parameters to search for a wide variety of keywords based on columns within the dataset. You can also change the number of data points that the query will gather for you by changing the limit number.

The API key has been placed in a seperate file that connects to the program file through these lines of code:
```
with open('api_keys.txt', 'r') as api_key_file:
   api_key = api_key_file.read().strip()
```

---

## Step 4: Place the Requested Data into a Data Frame using Pandas
Now that you have queried the data, you can quickly add the place the information into a data frame using pandas, as shown below:
```
results = data.get('results', [])

df = pd.DataFrame(results)
```
With that, you can now manipulate the data frame in the same way that you would any other pandas data frame in Python. 

---

## Step 5: Clean the Data for Analysis Purposes
Now that you have a dataframe that contains the data that you wanted, you can now clean the data for use.  
For my purposes, I intend to use the termination and report dates as datetime variables, so I will first make that change:
```
df['dt_report_date'] = pd.to_datetime(df['report_date'])
df['dt_termination_date'] = pd.to_datetime(df['termination_date'])
```
I would also like to seperate the year, month, and day from the report date variable:
```
df['report_year'] = df['dt_report_date'].dt.year
df['report_month'] = df['dt_report_date'].dt.month
df['report_day'] = df['dt_report_date'].dt.day
```
Finally, I will select the columns that I will need for my exploratory analysis and dashboard creation:
```
df = df.loc[:,['city', 'state', 'address_1', 'postal_code', 'classification', 'reason_for_recall', 'product_description', 'product_quantity', 'status', 'dt_report_date', 'dt_termination_date', 'report_year', 'report_month', 'report_day']]
```

Here is a portion of the dataset in a streamlit chart:
![Look at this wonderful chart!](/assets/images/data_collected.png "Data Frame")

---
---

## Ethics and Conclusions
In conclusion, the website that I added a link to earlier in this post can guide you to the help sheets that the FDA has created to additionally help with queries. By using the API provided by the United States government, this data is being willingly provided to the public for private research purposes. As long as API keys are kept private, this data is ethical and good for use. The next blog post will further detail the exploratory data analysis that I completed following this data collection. 


### These are all of the steps I took to query the OpenFDA API. All of the data is in string form, which can be easily changed using methods described in this super useful online book, [Python for Data Analysis](https://wesmckinney.com/book/data-cleaning).
