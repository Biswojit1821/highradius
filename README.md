# highradius
Order Amount Prediction



Objective of Tech Track (Machine Learning) 
Build a Machine Learning model to predict the order amount that customers can place in the upcoming days. 
Business Overview 
Introduction to B2B Operations: 
The B2B world operates differently from the B2C or C2C world. Businesses work with other businesses on credit. When a buyer business orders goods from the seller business, the seller business issues an invoice for the same. This invoice for the goods contains various information like the details of the goods purchased and when it should be paid. 
The simplest definition of accounts receivable is money owed to an entity by its customers. Correspondingly, the amount not yet received is credit and, of course, the amount still owed past the due date is Account receivables. A more formal definition of A/R is: 
“Accounts Receivable'' represents money owed by entities to the firm on the sale of products or services on credit. In most business entities, accounts receivable is typically executed by generating an invoice and either mailing or electronically delivering it to the customer, who, in turn, must pay it within an established timeframe, called credit terms or payment terms.”

Credit Check Department:
When a client receives an order, he validates the customer.
Then the client proceeds with verifying the available credit limit of the customer.
Once the credit limit gets verified, the client proceeds to check the purchase order sent to him by the customer.
Collecting purchase order from customers for inventory check
Calculating the exposure for a particular customer
Looking after the entire process of order inflow
Help the company provide services and products supply without hampering the cash inflow. 

Problem Statement for ML Model 
The objective of the first half of the summer internship project is:
To build a Machine Learning Model to predict the order amount, customers might make in the upcoming days.

You will be receiving an orders dataset that contains the past orders information and behavior of various buyers. Based on the previous orders patterns, the ML model needs to predict what will be the amount of orders the customer is going to place in the upcoming days. 
HIGH LEVEL REQUIREMENTS OF APPLICATION 
Specifically, below are the major aspects of the application that needs to be developed. The details for each of the below is provided in the functional overview section. 

Order Dataset: 
HighRadius will provide you with an order dataset which you need to parse and process. 
AI Support in the application: 
a. Add support for predicting the order amount for upcoming n days. 
b. UI should have a button to trigger the prediction of order amount. 
c. Order amount needs to be persisted across sessions in the UI.


FUNCTIONAL OVERVIEW 
Order Dataset: 
Download the dataset Link.
The dataset Below is the sample CSV file screenshot.










List of all the fields part of dataset are as follows: 
- CUSTOMER_ORDER_ID 
- SALES_ORG 
- DISTRIBUTION_CHANNEL
- DIVISION
- RELEASED_CREDIT_VALUE
- PURCHASE_ORDER_TYPE
- COMPANY_CODE
- ORDER_CREATION_DATE
- ORDER_CREATION_TIME
- CREDIT_CONTROL_AREA
- SOLD_TO_PARTY
- ORDER_AMOUNT
- REQUESTED_DELIVERY_DATE
- ORDER_CURRENCY
- CREDIT_STATUS
- CUSTOMER_NUMBER


Refer to this link for detailed description of column headers. 
AI Prediction of upcoming orders in a given time frame: 
As part of the problem statement, the amount of order(s) that can be placed by a customer will be predicted. 
The Predict button will be located towards the right and over the order grid.
Clicking on the Predict button will populate the Predicted Order Amount column.
Milestone 1 - Data Sanity ( by using Numpy and Pandas)
Use the PRS dataset to create a dataframe
Check the description of the dataframe
Check the shape of the dataframe
Check the data frame informations
Check for the Null values in the dataframe
Replace all the null values with "NaN"
Change the format of date columns - "ORDER_CREATION_DATE" to datetime[64] with the format as "%Y%m%d"
Do the same activity for the other date field i.e. "REQUESTED_DELIVERY_DATE" to datetime[64] with the format as "%Y%m%d"
Sanity check - Check how many records are having order date greater than the delivery date
Remove those records where order date is greater than the delivery date 
Check the number of records where the “ORDER_AMOUNT” field is having “-” in it.
Replace “-” with “” from the “ORDER_AMOUNT” field. 
Check the number of records where the “ORDER_AMOUNT” field is having “,” in it..
Replace “,” with “.” from the “ORDER_AMOUNT” field. 
Count the number of records where the order date and the delivery date are same
Count the number of records for each currency type by using the field “'ORDER_CURRENCY'”
Create a new column in the existing dataframe as “'amount_in_usd'” and convert all the non-USD currencies in USD and store them in the same column. 
Check for values “0” in the “'amount_in_usd” column. 
Create a new column in the existing dataframe “unique_cust_id” by adding 'CUSTOMER_NUMBER' and 'COMPANY_CODE'
Milestone 2 - EDA
Create a Histogram on DISTRIBUTION_CHANNEL
Create a Pie Chart on ORDER_CURRENCY
Create a line chart PURCHASE_ORDER_TYPE and DISTRIBUTION_CHANNEL
Create a line plot on ORDER_CREATION_DATE and amount_in_usd
Create a boxplot on ORDER_AMOUNT	to find out the outliers
Create a barchart on COMPANY_CODE	 and ORDER_AMOUNT
Milestone 3 - Feature Engineering and Selection

Check for the outliers in the “amount_in_usd” column and replace the outliers with appropriate values, discussed in the sessions.
Label encoding or One hot Encoding on all the categorical columns 
Log Transformations on continuous columns 
Try to extract new features by grouping existing columns 
Create a heatmap to find correlation between the columns
Try to identify important or relevant columns for feature extraction

Note - All of you Introduce a particular module (Link Attached) for datetime manipulation. 

Milestone 4 - ML Models and Evaluations
 Modify the dataset to pass into any type of machine learning models. 
Try different machine learning models like - 
Linear Regression
Support Vector Machine 
Decision Tree
Random Forest 
AdaBoost
Xgboost etc. 
Perform Regression model evaluations like MSE, RMSE, R-Square etc.
Compare the accuracies of all the models 
Select the best possible model
Perform Hyperparameter tuning, select best hyperparameters by using appropriate algorithms
Come up with the best possible model accuracy.

Glossary
Order: 
A document which is issued by a buyer to a seller when he wants some goods to be purchased. 
Credit limit: 
Amount that can be utilized by the customer without immediately paying back to the seller.
Exposure: 
The amount already utilized by the customer from his credit limit.
Blocked Order: 
When a customer tries to place an order above his remaining credit limit i.e., credit limit - exposure.
B2B: Business to Business 
B2C: Business to Consumer 
C2C: Consumer to Consumer 
