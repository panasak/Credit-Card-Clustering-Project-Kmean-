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
* CUSTID : Identification of Credit Card holder (Categorical)
* BALANCE : Total amount of money that you owe to your credit card company
* BALANCEFREQUENCY : How frequently the Balance is updated, score between 0 and 1 (1 = frequently updated, 0 = not frequently updated)
* PURCHASES : Amount of purchases made from account
* ONEOFFPURCHASES : Maximum purchase amount done in one-go
* INSTALLMENTSPURCHASES : Amount of purchase done in installment
* CASHADVANCE : Cash in advance given by the user
* PURCHASESFREQUENCY : How frequently the Purchases are being made, score between 0 and 1 (1 = frequently purchased, 0 = not frequently purchased)
* ONEOFFPURCHASESFREQUENCY : How frequently Purchases are happening in one-go (1 = frequently purchased, 0 = not frequently purchased)
* PURCHASESINSTALLMENTSFREQUENCY : How frequently purchases in installments are being done (1 = frequently done, 0 = not frequently done)
* CASHADVANCEFREQUENCY : How frequently the cash in advance being paid
* CASHADVANCETRX : Number of Transactions made with "Cash in Advanced"
* PURCHASESTRX : Numbe of purchase transactions made
* CREDITLIMIT : Limit of Credit Card for user
* PAYMENTS : Amount of Payment done by user
* MINIMUM_PAYMENTS : Minimum amount of payments made by user
* PRCFULLPAYMENT : Percent of full payment paid by user
* TENURE : Tenure of credit card service for user
* 
## EDA
I looked at the distributions of the data. Below are a few highlights from the pivot tables.

![alt text](https://github.com/Panasak/Thailand_House_Prices_Predictor/blob/main/data_clean/sactter_plot.png)
![alt text](https://github.com/Panasak/Thailand_House_Prices_Predictor/blob/main/data_clean/heat_plot.png)
![alt text](https://github.com/Panasak/Thailand_House_Prices_Predictor/blob/main/data_clean/box_plot.png)
![alt text](https://github.com/Panasak/Thailand_House_Prices_Predictor/blob/main/data_clean/bar_plot.png)
## Model Building
First I delete the rows with missing data from the dataset. These rows only make up a very small amount of data compare to the whole dataset and thus could be deleted safely. I then scaled the data using Standard Scaler from sklearn library. This is done so that the variables are bing processed with the same weight. This is a necessary step with working with distance based algorithm such as k-mean clustering. I then optimized the model using the elbow method the find the optimal number of clusters

## Model Performance
I found that the optimal number of clusters in this dataset is 4. Below is the visual representation of how the data would clustered for each variables.
