# STA 208 Project

## COVID-19 Analysis

### Group Members:  
* Zhi Zhang
* Xiaohan Hu
* Yanhao Jin 917793578
* Xialin Sang

## Data Sources

#### COVID-19 Data Set 

https://github.com/CSSEGISandData/COVID-19 
https://github.com/CSSEGISandData/COVID-19/tree/master/csse_covid_19_data/csse_covid_19_time_series 

#### Bed Data Set 

https://www.kaggle.com/ikiulian/global-hospital-beds-capacity-for-covid19#hospital_beds_global_regional_v1.csv 

#### State Population Dataset

https://www.census.gov/data/tables/time-series/demo/popest/2010s-counties-detail.html https://www.census.gov/content/census/en/data/datasets/time-series/demo/popest/2010s-state-total.html 

You are able to reach out all files in GitHub: 

## Data Proprocessing
You are able to reach out all preprocessed date in: [Data](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Data)  
## Visualization
Before the analysis, we do a basic visualization for different situations in each state using folium map. You can find steps and results in [visualization.ipynb](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/visualization.ipynb). This provides some insights for comparing the situations of COVID-19 in different states.

Besides, we are access to the average temperature in each state. We visualize the time series data for COVID-19 cases as well as average temperature series in selected states in this notebook [Visualization for time series data](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20Visualization%20for%20Time%20Series%20Data.ipynb). 

## Autoregression Analysis and Prediction
For predicting the confirmed and deaths cases, it is natural to using autoregression model. In the notebook [Autoregression without using other features](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20Autoregression%20Analysis%20without%20Temperature.ipynb), we fit ARIMA model for selected states without using other features.

## GCNN
We also considered the GCNN (Graph Convulutional Neural Netork). We used it to construct the zip code level graph and predicted the response: daily cov-19 cases, both for confirmed, and deaths. We considered using the past five days cases number as features. The notebook [GCNN without temperature](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%GCNN%without%Temperature.ipynb) showed the details of methods and results. At the same time, we also included the temperature as additionaal features, in the notebook [GCNN with temperature](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%GCNN%with%Temperature.ipynb). 



## Conclusion

