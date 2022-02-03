# Credit Card Clustering Project: Project Overview
This project uses k-mean clustering to clusters credit card users into different groups based on their balance and various spending habits.
* Create a tool that clusters credit card users into different groups to help credit card providers identify the right audience when creating marketing campaigns
* Optimized k-mean cluster analysis using the Elbow Method to reach the best model
## Code and Resources Used
* **Python Version:** 3.7
* **Packages:** pandas, numpy, matplotlib, seaborn, sklearn
* **Kaggle data:** https://www.kaggle.com/arjunbhasin2013/ccdata
## About the data
The data contain the follwing columns
* House Listing Titles
* House Listing Descriptions
* Addresses
* Areas in Square Yard
* Number of Bedrooms
* Number of Bathrooms
* Prices
* Listing Dates
* Status (New or Second Hand)
## Data Cleaning
After scraping the data. I needed to clean it up so that it was usable for our model. I made the followinng changes and created the following variables:
* Parsed numeric data out of prices
* Made columns for subdistricts, districts, and provinces
* Removed rows without bedrooms or bathrooms
* Transformed listing datas or numerical value
* Made columns for it different keywords were listed in the descriptions:
  * school
  * univeristy
  * airport
  * city
  * housing estate
  * view
* Made a columns for titles and descriptions lengths
## EDA
I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights from the pivot tables.

![alt text](https://github.com/Panasak/Thailand_House_Prices_Predictor/blob/main/data_clean/sactter_plot.png)
![alt text](https://github.com/Panasak/Thailand_House_Prices_Predictor/blob/main/data_clean/heat_plot.png)
![alt text](https://github.com/Panasak/Thailand_House_Prices_Predictor/blob/main/data_clean/box_plot.png)
![alt text](https://github.com/Panasak/Thailand_House_Prices_Predictor/blob/main/data_clean/bar_plot.png)
## Model Building
First I transformed the categorical variables into dummy variables. I also split the data into train and test sets with a test size of 33%
I tired three different models and evaluated them using Mean Absolute Error. I chose MAE because it is relatively easy to interpret and outliers aren't particularly bad in for this type of model.
I tried three different models:
* **Multiple Linear Regression** - Baseline for the model
* **Lasso Regression** - Because of the sparse data from the many categorical variables. I thought a normalized regression like lasso would be effective
* **Random Forest** - Again, with the sparsity associated with the data, I thought that this would be a good fit
## Model Performance
The Random Forest model outperformed the other approaches on the test and validation sets
* **Random Forest:** MAE = 4411561.95
* **Linear Regression:** MAE = 441239550501459.25
* **Lasso Regression:** MAE = 6423036.02
## Productization
In this step, I built a flask API endpoint that was hosted on a local webserver by following along with the TDS tutorial in the reference section above. The API endpoint takes in a request with a list of values for a house listing and return an estimated price.





