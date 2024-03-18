### Project Name: VAR Models Forecast UK economy

The idea of this prohect is to study the time series medels VAR in order to forecast UK economy for the years 2010-2016, to do that we will develop 3 models VAR,VECM and VARMAX in order to see whichone
explained better the UK economy 

Table of Contents
Introduction
Features
Installation
Usage
Contributing
License

### Introduction

The 2008 crisis  produced an increase  of  unemployment, debt and adjustments on the public sector throughout cuts on the public spending plus tax rises which  favored the impoverishment of the middle classes and with it the rethinking of our society model.\\~\\ 
This has been reflected in a radicalization of society and the rise of new extreme left and right parties who openly question the model of society that we have enjoying since the Second World War. 

These tensions have put the focus on the ability of economists to predict economic crises or design policies capable of softening their consequences in society

The idea of this project  is to compare the predictions made by three models and see which of the three best captures the behavior of a set of macroeconomic variables with the data coming from "A millennium of macroeconomic data" from the Bank of England, for the period 2010-2016. 

Features
List the key features of the project.



### Data 
the Data we are going to use is  "A millennium of macroeconomic data" from the Bank of England. This dataset contains a broad set of macroeconomic and financial data for the UK stretching back in some cases to the C13th and with one or two benchmark estimates available for 1086.

After selecting our variables and and drooping null values we end up with a data sample with 10 variables annualized or the period  1922-2016 on UK.
#Real GDP of England at market prices
#Real consumption
#Real investment
#Employment
#$ Oil prices
#UK Public sector debt
#Terms of trade 
#Public sector Total Managed Expenditure
#M1
#House prices index 

### Methodology:
1. Data Preprocessing: Clean and preprocess the raw data, handling missing values,and applying logaritms and first differences transformations 
2. Model Selection: Choose the appropriate lag order for the VAR and for the VECM. In the case of the VARMAX we compare 36 different parameters combinations to pick the best one.
3. Model Training: Estimate the parameters of the VAR model using historical data coming from the Dataset mentioned above 
4. Forecasting: Generate forecasts for key economic indicators based on the trained VAR model.
5. Evaluation:  Mean Absolute Error

## Results

After runing the 3 different types of models we end up picking the VARMAX moel since it is the one with the highest accurancy.
THe resutls of the 3 models are quite similar underestimating the GDP, employment TOT, total managed expenditure  and overestimating the consumption, Investment  the M1 and the houses pricing 
They provide more poor estimations more international variables  the oil prices and the Terms of trade (which depends on the rest of the wordl as well)

## Usage:
1. Clone this repository: https://github.com/enricgarciapaya/Final_Project_VAR.git
2. Install the required dependencies
!pip install pandas, numpy, matplotlib, seaborn, statsmodels, scikit-learn, scipy

And import the following packages:

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
import seaborn as sns
from statsmodels.tsa.seasonal import seasonal_decompose
import statsmodels.graphics.tsaplots as sgt
import statsmodels.tsa.stattools as sts
from statsmodels.stats.stattools import durbin_watson
from statsmodels.tsa.api import VAR
from statsmodels.tsa.api import VECM
from statsmodels.tsa.vector_ar.vecm import select_coint_rank
from statsmodels.tsa.vector_ar.vecm import coint_johansen
from statsmodels.tsa.statespace.varmax import VARMAX
from sklearn import metrics
from sklearn.model_selection import ParameterGrid
import scipy
import warnings
warnings.filterwarnings('ignore')

3. Run the main script to execute the forecasting process
VAR.ipynb

Contributing
The main contributors to this project have been, on the theory side the youtube chanel "Econometria" and his play list regarding time series, plus all time series analysis notes coming from Daniel Ferrer Lazaro. 
On the code side the work from Luca Donghi has been esential in order to perform statistics in the most efficent way .



Contact
enric.garcia.paya@hotmail.com

