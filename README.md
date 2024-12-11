## Introduction:

This project analyzes various features related to power outages to identify key factors influencing their duration. Using statistical analysis we uncover patterns in outage duration and propose predictive models to keep people informed and prepared for the durations of outages. We are focusing on one question in specific: 
> ### **What factors contribute to the duration of a power outage?**

The dataset we are working with has 1534 rows and 58 columns, but while we looked at a lot of these columns to figure out which ones were most important to answering our question, we ended up finalizing a couple columns that we wanted to focus our exploration on: `OUTAGE.DURATION`, `NERC.REGION`, `CAUSE.CATEGORY`, and `CLIMATE.CATEGORY`. `OUTAGE.DURATION` is the time that the outage lasted in minutes, saved as an integer. *NERC* stands for North American Electric Reliability Corporation, so `NERC.REGION`s are essentially U.S. regions sectioned off by electricity supply. `CAUSE.CATEGORY` is a string that represents what caused the power outage and `CLIMATE.CATEGORY` is a string value of either 'cold', 'warm', or 'normal' based on what the climate is like in the area where the power went out.

---


## Data Cleaning and Exploratory Data Analysis

#### **Data Cleaning:**

Data was preprocessed to combine date and time fields for outage start and restoration times. Since we were testing the distribution of essentially every column, all of the columns had to be cleaned. Most of the data was already cleaned for us, but the main thing we had to do was clean up how the time that each outage started and ended was stored. When we started looking at the data, there were two columns for each `OUTAGE.START.DATE`, `OUTAGE.START.TIME`, `OUTAGE.RESTORATION.DATE`, and `OUTAGE.RESTORATION.TIME`. Instead of this, we combined the date and time fields in order to get `OUTAGE.START` and `OUTAGE.RESTORATION`. This allowed us to be more precise with the data and allow us to not just look at date and time separately. Below is what the first couple rows of the data looked like:

![Data Head](images/full_data_head.png)


#### **Exploratory Analysis:**

Exploratory visualizations and analyses were conducted to understand the distribution of outage durations and other variables, as well as relationships between variables. We used histograms for the numerical values, bar graphs for categorical variables, and made scatter plots of quantitative variables against outage duration. We also created box plots of outage duration conditional on categorical variables and a pivot table of mean outage durations, conditioned on climate and cause categories.

#### **Univariate Analysis**

We examined the distribution of individual columns first to better understand how each feature varied across the dataset. This analysis helps identify patterns, outliers, and the overall spread of the data, giving us insights into the individual characteristics of each feature. Below is a visualization showing the distribution of `OUTAGE.DURATION`. The plot reveals that the data is skewed to the right suggesting that the majority of the outage durations are relatively short and are typically shorter than 5000 minutes, though there are a few instances where the outage lasted much longer than the average.

![1 Column Distribution of OUTAGE.DURATION](images/1col_dist_duration.png)

We also looked at the distribution of categorical data such as `CAUSE.CATEGORY`, which showed us that the majority of power outages seemed to be caused by severe weather. 

![1 Column Distribution of CAUSE.CATEGORY](images/1col_dist_cause.png)



#### **Bivariate Analysis**

To understand how outage duration relates to other features, we explored potential correlations and trends between the `OUTAGE.DURATION` column and other columns such as `CUSTOMERS.AFFECTED`. The below scatter plot displays this relationship, which shows that there is not much of a correlation other than that short power outages that didn't affect many people were common.

![Customers Affected vs Outage Duration](images/duration_vs_affected.png)

#### **Interesting Aggregates**

![Pivot Table](images/pivot_table.png)

---

## Assessment of Missingness


After analysing the missingness in the dataset, we determined that `OUTAGE.DURATION` is likely NMAR. This conclusion is based on the hypothesis testing results from a permutation test we conducted, where the p-value for the relationship between missingness in `OUTAGE.DURATION` and the feature `miss` was not statistically significant which helps us conclude that the missingness in `OUTAGE.DURATION` is not due to the missingness in other columns.

![Outage Duration Missingness](images/duration_nmar.png)

On the other hand, `CLIMATE.CATEGORY` seems to be MAR with respect to `TOTAL.SALES` due to the significant p-value in the permutation test we conducted.

![Climate Category Missingness](images/climate_mar.png)



---


## Hypothesis Testing

We had a couple of hypothesis tests that we were looking at:

#### OUTAGE DURATION ACROSS NERC REGION
- Null Hypothesis: Outage duration is the same across all NERC regions
- Alternative Hypothesis: Outage duration is different across NERC regions
- Test Statistic: Total Variation Distance
	- We used TVD as the test statistic to compare categorical distributions between two groups. It quantifies the difference between the observed distribution and the expected distribution if the null hypothesis were true.
- At a significance level of 0.05, the null hypothesis is rejected, suggesting that NERC region may be correlated with outage duration.



#### OUTAGE DURATION ACROSS CAUSE CATEGORIES
- Null Hypothesis: Outage duration is the same across all cause categories
- Alternative Hypothesis: Outage duration is different across cause categories
- Test Statistic: Total Variation Distance
	- We use TVD to measure how different the distribution of outage durations is across different cause categories.
- At a significance level of 0.05, the null hypothesis is rejected,suggesting that cause category may be correlated with outage duration.


#### OUTAGE DURATION ACROSS CLIMATE CATEGORIES
- Null Hypothesis: Outage duration is the same across all climate categories
- Alternative Hypothesis: Outage duration is different across climate categories
- Test Statistic: Total Variation Distance
	- We used TVD again to measure differences in the distribution of outage durations between climate categories
- At a significance level of 0.05, the null hypothesis is rejected, suggesting that climate category may be correlated with outage duration.

---


## Framing a Prediction Problem

Goal: Predict the duration of a power outage given certain conditions.

Features: ...

Target: ...

---


## Baseline Model

Model Used: ...

Performance Metrics:...

---

## Final Model

Improved Model: ...

Feature Importance: ...

Performance Comparison: ...

---

## Fairness Analysis

At a significance level of 0.05, the null hypothesis is failed to be rejected and the model may be fair between areas with low and high populations.

Visual

---

##### Kristina Nguyen & Durga Nair
