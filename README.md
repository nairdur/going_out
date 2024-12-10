## Introduction:

This project analyzes various features related to power outages to identify key factors influencing their duration. Using statistical analysis we uncover patterns in outage duration and propose predictive models to keep people informed and prepared for the durations of outages. We are focusing on one question in specific: 
> What factors contribute to the duration of a power outage?
The dataset we are working with has 1534 rows and 58 columns, but while we looked at a lot of these columns to figure out which ones were most important to answering our question, we ended up finalizing a couple columns that we couldn't do our analysis without: `OUTAGE.DURATION`, `OUTAGE.START`, `OUTAGE.RESTORATION`, `NERC.REGION`, `CAUSE.CATEGORY`, and `CLIMATE.CATEGORY`. 


**Data Cleaning and Exploratory Data Analysis**

Data Cleaning:

Data was preprocessed to combine data and time fields for outage start and restoration times. **is this a datetime var prior to this?**


Exploratory Analysis:
Exploratory visualizations and analyses were conducted to understand the distribution of outage durations and other variables, as well as relationships between variables. We used histograms for the numerical values, bar graphs for categorical variables, and made scatter plots of quantitative variables against outage duration. We also created box plots of outage duration conditional on categorical variables and a pivot table of mean outage durations, conditioned on climate and cause categories.



Frequency of outages by cause (e.g., storms, equipment failure).

Distribution of outage durations.

Trends over time or location.

**Assessment of Missingness**

Analyze missing data and its potential bias.


Types of Missingness: MCAR, MAR, NMAR?

Impact on Analysis: 


**Hypothesis Testing**

...

Summarize the statistical test used (e.g., t-tests, chi-squared tests), the results, and whether the hypothesis was supported.


**Framing a Prediction Problem**

Goal: Predict the duration of a power outage given certain conditions.

Features: ...

Target: ...


**Baseline Model**

Model Used: ...

Performance Metrics:...


**Final Model**

Improved Model: ...

Feature Importance: ...

Performance Comparison: ...


**Fairness Analysis**

At a significance level of 0.05, the null hypothesis is failed to be rejected and the model may be fair between areas with low and high populations.

Visual

**Authors**

Kristina Nguyen

Durga Nair
