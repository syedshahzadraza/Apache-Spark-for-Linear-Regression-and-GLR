# Project: Walmart Sales Forecasting

@author: Syed Shahzad Raza

<h1>Table of Contents<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#Project-Statement" data-toc-modified-id="Project-Statement-1"><span class="toc-item-num">1&nbsp;&nbsp;</span>Project Statement</a></span><ul class="toc-item"><li><span><a href="#Project-Overview" data-toc-modified-id="Project-Overview-1.1"><span class="toc-item-num">1.1&nbsp;&nbsp;</span>Project Overview</a></span></li><li><span><a href="#Use-Case" data-toc-modified-id="Use-Case-1.2"><span class="toc-item-num">1.2&nbsp;&nbsp;</span>Use Case</a></span></li><li><span><a href="#Data-Acquisition" data-toc-modified-id="Data-Acquisition-1.3"><span class="toc-item-num">1.3&nbsp;&nbsp;</span>Data Acquisition</a></span></li></ul></li><li><span><a href="#Technology-Choice" data-toc-modified-id="Technology-Choice-2"><span class="toc-item-num">2&nbsp;&nbsp;</span>Technology Choice</a></span></li><li><span><a href="#Data-Set" data-toc-modified-id="Data-Set-3"><span class="toc-item-num">3&nbsp;&nbsp;</span>Data Set</a></span></li><li><span><a href="#Model-Definition" data-toc-modified-id="Model-Definition-4"><span class="toc-item-num">4&nbsp;&nbsp;</span>Model Definition</a></span></li></ul></div>

## Project Statement
Our objective is to use historical data from 45 Walmart stores located in different regions to predict the department-wide sales for each store.

### Project Overview

The intent behind this study is to build an end-to-end data science project covering various aspects of CRISP-DM process model including business understanding, data understanding, data preparation, modeling and evaluation. 

The project is divided into four phases. 

* **Phase I**: Data Exploration and Pre-Processing ([click here to load](Phase_I_Data_Exploration_and_Pre_Processing.ipynb))

    Rigorous data analysis & visualization through Exploratory Data Analysis to build a better business understanding using data exploration.


* **Phase II**: Feature Engineering ([click here to load](Phase_II_Feature_Engineering.ipynb))

    Scaling, imputation and encoding tasks to modify existing and create new features.


* **Phase III**: Model Training ([click here to load](Phase_III_Model_Training.ipynb))

    Training of machine learning models using the SparkML pipeline framework, including model selection (a.k.a. hyperparameter tuning)


* **Phase IV**: Model Evaluation ([click here to load](Phase_IV_Model_Evaluation.ipynb))

    Implementation of different performance metrics and calculation of accuracy of results. 


### Use Case
Walmart saw a turnover of more than half a trillion (USD518 billion) in 2019, more than double that of its closest competitor and ecommerce giant Amazon.

Here’s a list of the top ten global retailers and their global sales revenue in 2019:

* Walmart: USD517.7 billion
* Amazon: USD213.8 billion
* Costco: USD144.4 billion
* Schwarz: USD130.4 billion
* Kroger: USD124.3 billion

(Source: [Forbes: Who Are The 10 Biggest Retailers In The World?](https://www.forbes.com/sites/callyrussell/2020/01/09/who-are-the-10-biggest-retailers-in-the-world/#6629363c3802))

These statistics alone make Walmart a gold mine for any data science study. 

### Data Acquisition
The data set is made available by Walmart [here](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting).

## Technology Choice
* Jupyter Notebook
* IBM Watson Studio
* Apache Spark
* Seaborn and Matplotlib

## Data Set
The data set contains historical data from 45 Walmart stores located in different regions. The task is to predict the department-wide sales for each store.

The data is stored in multiple files.

<p style="background:black">
<code style="background:black;color:white">stores.csv, features.csv, test.csv and train.csv</code>
</p>

**stores.csv**

This file contains anonymized information about the 45 stores, indicating the type and size of store.

**train.csv**

This is the historical training data, which covers to 2010-02-05 to 2012-11-01. Within this file you will find the following fields:

- Store - the store number
- Dept - the department number
- Date - the week
- Weekly_Sales -  sales for the given department in the given store
- IsHoliday - whether the week is a special holiday week

**test.csv**

This file is identical to train.csv, except we have withheld the weekly sales. You must predict the sales for each triplet of store, department, and date in this file.

**features.csv**

This file contains additional data related to the store, department, and regional activity for the given dates. It contains the following fields:

- Store - the store number
- Date - the week
- Temperature - average temperature in the region
- Fuel_Price - cost of fuel in the region
- MarkDown1-5 - anonymized data related to promotional markdowns that Walmart is running. MarkDown data is only available after Nov 2011, and is not available for all stores all the time. Any missing value is marked with an NA.
- CPI - the consumer price index
- Unemployment - the unemployment rate
- IsHoliday - whether the week is a special holiday week

For convenience, the four holidays fall within the following weeks in the dataset (not all holidays are in the data):

- Super Bowl: 12-Feb-10, 11-Feb-11, 10-Feb-12, 8-Feb-13
- Labor Day: 10-Sep-10, 9-Sep-11, 7-Sep-12, 6-Sep-13
- Thanksgiving: 26-Nov-10, 25-Nov-11, 23-Nov-12, 29-Nov-13
- Christmas: 31-Dec-10, 30-Dec-11, 28-Dec-12, 27-Dec-13

## Model Definition
We will evaluate the performance of two machine learning models.
* Linear Regression
* Generalized Linear Regression

Moreover, a model selection technique (a.a.a. hyperparameter tuning) will be implemented using Train-Validation Split.
