

### Introduction

In this project we are forecasting the natural gas consumption in the USA by the 
commercial sector. The data is fetched from the US Energy Information Administration website whose, at
the moment, active link is [this.](https://www.eia.gov/totalenergy/data/browser/index.php?tbl=T02.03#/?f=M&start=200001)

### Data
The data shows the monthly energy consumption in Trillion BTU (British Thermal Unit) starting from 1973 to till now. We removed the rows that showed the sum of monthly values as a part of data cleaning. 

The data has some seasonality showing higher values in the January and lowest on August. Therefore, we have to account for seasonality while modeling our data.

### Forcasting Model

#### SARIMA
At, first we did the grid search for finding the optimal parameters for the SARIMA model. Then, we modeled the final model with the optimal order that we found from the grid search.

#### Auto-SARIMA
We also used the `pmdarima` library to automatically search the orders for the SARIMA model. It also uses the grid search however, it is easier to set-up rather then the manual grid search. 

#### FB Prophet
Prophet is the easy-to-use forecasting algorithms based on additive technique from Facebook. It is built to use by both technical and non-technical users. It automatically detects the seasonality and robust to outliers as well as missing value. It is a auto-forecsting tool that need very minimal setup and pre-processing. 

### Results

In our analysis, SARIMA model from the `pmdarima` library outperformed the any other techniques. The MAPE(Mean Absolute Percentage Error) on the test data for SARIMA model was 4% for auto-sarima whereas Prophet gave us 10% error. Therefore, SARIMA was better for forecasting then the Prophet in our case. 

### Libraries Used
Please find the libraries used in the `requirement.txt` file.