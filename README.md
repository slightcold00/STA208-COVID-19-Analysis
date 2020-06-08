# STA 208 Project

## COVID-19 Analysis

### Group Members:  
* Zhi Zhang 917834518
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

### Guideline

The files are supposed to read in this order:
1. Basic visualization: [Condirmed and Death Situation in Each State](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Plots/Condirmed_case_and_death_case.html), [Hopsital Beds and Death Rate Situation in Each State](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Plots/Hopsital_Beds_and_Death_Rate.html), [Population and Confirmed Situation in Each State](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Plots/Population_and_confirmed_case.html), [visualization.ipynb](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/visualization.ipynb) and [Visualization for time series data](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20Visualization%20for%20Time%20Series%20Data.ipynb). 

2. Autoregression analysis: [Autoregression without using other features](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20GCNN%20without%20Temperature.ipynb) and [Autoregression using other features](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20GCNN%20with%20Temperature.ipynb).

3. GCNN: [GCNN without temperature](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20GCNN%20without%20Temperature.ipynb) and [GCNN with temperature](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20GCNN%20with%20Temperature.ipynb)

4. Conclusion and Discussion: [Recommended model using autoregression analysis](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20Recommended%20Autoregression%20Model%20for%20Prediction.ipynb) and [A Brief Discussion on changing temperature in test data](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20Discussion%20for%20Changing%20Average%20Daily%20Temperature.ipynb).

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

To avoid overfitting on the training set, we did not add to many features about the daily temperature. For predicting the confirmed cases, we try a new model using daily average temperature as a potential feature. For predicting the death cases, we fit two different models, one using temperature as potential features and the other using temperature and confirmed cases as potential features. Details are provided in this notebook [Autoregression using other features](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20GCNN%20with%20Temperature.ipynb).

## GCNN
We also considered the GCNN (Graph Convulutional Neural Netork). We used it to construct the zip code level graph and predicted the response: daily cov-19 cases, both for confirmed, and deaths. We considered using the past five days cases number as features. The notebook [GCNN without temperature](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20GCNN%20without%20Temperature.ipynb) showed the details of methods and results. At the same time, we also included the temperature as additionaal features, in the notebook [GCNN with temperature](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20GCNN%20with%20Temperature.ipynb). 

## Conclusion and Discussion
### Discussion on Autoregression analysis
In this notebook [Recommended model using autoregression analysis](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20Recommended%20Autoregression%20Model%20for%20Prediction.ipynb), we give a brief summary of recommended prediction model. We see that for predicting the death cases, it is useful to add average temperature as a potential feature. For predicting the confirmed cases, the autoregression model without using temperature is already good, especially for Pennsylvania, Florida and Washington.

In this notebook [A Brief Discussion on changing temperature in test data](https://github.com/yanhaojin/STA208-COVID-19-Analysis/blob/master/Notebooks/STA208%20COVID-19%20Discussion%20for%20Changing%20Average%20Daily%20Temperature.ipynb), we give a brief discussion on changing average temperature on the test data to see what would happen if the average temperature was 10 degrees higher and 10 degrees lower. However, we should be careful on this issue. There are many other biological features that will affect the activity of virus, for example, the health condition for each confirmed case. 

Due to the limitation, we did not have the access to these data. Besides, we can not make casual statements on the relationship between temperature and death cases. This result is not quite reliable and need to be improved further.

### Discussion on GCNN

We considered the GCNN (Graph Convolutional Neural Network) + (MLP) to represent the structure between instances (zipcodes). We learned the structure through our model. We used it to predict the zip code level and daily covid-19 cases. We mapped the temperature data from the source and linked it with the covid-19 data by zipcodes. Our model can predict granular level (zipcode) cases and is flexible to delete and add other features, also the model can be extended because the structure of our model can be varied as GCNN+MLP or GCNN+RNN, or even GCNN+RL. 

- Include Temperatures vs Not Include

Overall, adding the temperatures signal eventually helps the learning model converges better, we see that under the same final iteration steps, the models have lower training and validation MSE compared to the basic model. 

- Complexity 

All of our GCNN results presented so far are kind of not fully trained - stopped before it can be improved further, due to time limit. The GCNN architecture is complex and requires better machines such as GPU to train, unfortunately, we don't have such facility at this moment, but we encouraged our professor and intreated readers to train fully to see the final result it can reach without resource limits. 

- Future Work

In later work, we would like to consider using with pre-defined adjacency matrix $A'$, other ways to build matrix such as using cases itself can also be considered. We may add it by using $\alpha A' + (1-\alpha) A$, as a combination of two. We will also consider the RNN to replace the feedforward structure. 

