# Introduction

The data in this website come from a dataset created by the Laboratory for Advancing Sustainable Critical Infrastructure at Purdue Univeristy (https://www.sciencedirect.com/science/article/pii/S2352340918307182). This dataset has a row for each power outage from Jan 2000- July 2016 in the United States that impacted atleast 50,000 customers or caused an unplanned firm load loss of atleast 300 MegaWatts. This dataset was used to perform for exploratory data analysis, assessment of missingness, and finally a permuatation test.

## Question

Does the Number of Power Outages Relate to the per Capita Real Gross State Product?

## Purpose

The Real Gross State Product is a measurement of the financial well being of the residents in each state, and it is a good indicator of the strength of a given state's economy. So the answer to this question gives a lose connection to how well a state's infrastructure performs based on the states economic strength.

# Exploratory Data Analysis

How the power outage data was cleaned and explored to reach further depth on questions to be answered. 

## Data Cleaning

### 1

The data from Purdue University's website is in a .xlsx excel sheet. In order to read it in certain rows and columns from the excel sheet had to be dropped in order to turn it into a usable dataframe in pandas. From the

### 2

Each power outage had an entry for the given outage's start day and start time separately, as well as the restoration start day and start time. These were both joined together to create a single column for the outage start, OUTAGE.START, and as column for the restoration date, OUTAGE.RESTORATION, which has the start time as a datetime object to the second of when the outage started, as well as when the restoration started respectively. 

### 3

The OUTAGE.DURATION column was divided by sixty in order to make it in minutes, which is a more understandable unit for the duration of power outages. 

### 4

 Two separate dataframes were created from this cleaned data that would be used throughout the rest of the research process. First is grouped_state, which has columns: 'MEAN.POP', 'MEAN.POP.URBAN', 'MEAN.GSP $', and 'OUTAGES.POP.NORM', and a row for each state that experienced a major power outage between the specified dates. 

- Mean.POP: The average population for each state over the instances of power outages
- MEAN.POP.URBAN: Average percentage of the state's population that is urban over the instances of power outages
- MEAN.GSP $: Average value of a given state's GSP over the instances of power outages
- OUTAGES.POP.NORM: The number of power per 100,000 people for the given dataset. 