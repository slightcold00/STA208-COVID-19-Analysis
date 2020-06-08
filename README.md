# STA 208 Project

## COVID-19 Analysis

### Group Members:  
* Zhi Zhang
* Xiaohan Hu 917861918
* Yanhao Jin 917793578
* Xialin Sang 917780316

## Raw Data Sources

#### COVID-19 Data Set 

https://github.com/CSSEGISandData/COVID-19 
https://github.com/CSSEGISandData/COVID-19/tree/master/csse_covid_19_data/csse_covid_19_time_series 

#### Bed Data Set 

https://www.kaggle.com/ikiulian/global-hospital-beds-capacity-for-covid19#hospital_beds_global_regional_v1.csv 

#### State Population Dataset

https://www.census.gov/data/tables/time-series/demo/popest/2010s-counties-detail.html https://www.census.gov/content/census/en/data/datasets/time-series/demo/popest/2010s-state-total.html 


## Data Proprocessing
You are able to reach out all preprocessed date in: [Data](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Data)  

## Visualization

Before the analysis, we do a basic visualization for different situations in each state using folium map. The results are:
* [Condirmed and Death Situation in Each State](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Plots/Condirmed_case_and_death_case.html)
* [Hopsital Beds and Death Rate Situation in Each State](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Plots/Hopsital_Beds_and_Death_Rate.html)
* [Population and Confirmed Situation in Each State](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Plots/Population_and_confirmed_case.html)

You can find steps and conclusions  in [visualization.ipynb](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/visualization.ipynb). 
This provides some insights for comparing the situations of COVID-19 in different states.

Besides, we are access to the average temperature in each state. In this part, we visualize the time series data for COVID-19 cases as well as average temperature series up to 05-24-2020 in selected states in this notebook [Visualization for time series data](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20Visualization%20for%20Time%20Series%20Data.ipynb). Based on the visualization above, it seems that the confirmed cases and death cases in California and Washington is related to their average temperatures because they have similar trend in general for California and Washington.

## Autoregression Analysis and Prediction
In this part, we use the number of confirmed and death cases during first 80 percents of days for our training data. And we use the number of confirmed and death cases during last 20 percents of days for our testing data to evaluate the model.

For predicting the confirmed and deaths cases, it is natural to using autoregression model. In the notebook [Autoregression without using other features](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20GCNN%20without%20Temperature.ipynb), we fit ARIMA model for selected states without using other features. 

To avoid overfitting on the training set, we did not add to many features about the daily temperature. Only average daily temperature is used in autoregression analysis. In this notebook [Autoregression using other features](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20GCNN%20with%20Temperature.ipynb), 

## GCNN
We also considered the GCNN (Graph Convulutional Neural Netork). We used it to construct the zip code level graph and predicted the response: daily cov-19 cases, both for confirmed, and deaths. We considered using the past five days cases number as features. The notebook [GCNN without temperature](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20GCNN%20without%20Temperature.ipynb) showed the details of methods and results. At the same time, we also included the temperature as additionaal features, in the notebook [GCNN with temperature](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%GCNN%with%Temperature.ipynb). 

## Conclusion and Discussion

In this notebook [Recommended model using autoregression analysis](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20Recommended%20Autoregression%20Model%20for%20Prediction.ipynb), we give a brief summary of recommended prediction model. We see that for predicting the death cases, it is useful to add average temperature as a potential feature. For predicting the confirmed cases, the autoregression model without using temperature is already good, especially for Pennsylvania, Florida and Washington.


>>>>>>> 189f0fe1f8a4d68fa48fdfa94960b01489064e69

