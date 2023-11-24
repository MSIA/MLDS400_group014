# MLDS400_group014

## Week 7 (ThanksGiving)       

This week is a ThanksGiving Week, everyone in our group is traveling, but we still had a meeting before ThanksGiving break to sit down and talk about what we had so far.

Summary of the meeting:               
Summarizing all the works we have, we think what we have now are linear models to predict the store return rate for one year data (with 22% R^2). We have talked about why we only have 22%. 
- Feature issue: we do not have a feature that has a strong prediction power, so this indicates we need to do more feature engineering.
- Model issue: linear model may not be too good for this much of data, we may need to consider other models that are more powerful in prediction, and tries a different model.

ROI possible direction:    
I think we have a good machine learning topic on predicting store return rate, we can analyze the result by the following 2 aspects.    
- Customer Satisfaction: Knowing which stores have a higher return rate and why can inform improvements in the saling of that particular store. This can lead to higher customer satisfaction and loyalty, as customers are more likely to be satisfied with their purchases.
- Regional Trends and Strategies: Analyzing return rates by store can reveal regional trends and preferences. This information can guide regional marketing strategies, inventory selection, and promotions to better align with customer preferences in different areas.


## Week 6

This week we have continued to create more features relating to the price, location and time of year and how they relate to return rate. We also have implemented logic to load in sensitive information (username, password) from a .env file so that we do not need to worry about commiting sensitive information. 

In addition, we also added data visualization used tableau which we used to learn in class. Check out the png file in the data_viz folder. The dashboard is super fun to explore, but we need more features to keep playing around with the data.

In the end, we fit a linear regression model based on selected features, the result shows multicollinearity. we may address it using Variance Inflation Factor, revise our features, scale data, explore other models, apply cross-validation, check statistical assumptions, and continuously refine the model with stakeholder feedback and iterative testing.

next week goal: 
* more data visualization 
* detect more features
* try more models other than linear regression.
* start to look at ROI

## Week 5  
This week, we have chose research question 5, and we start to do some SQL query to select our features, after feature engineerings, we will start data cleaning and EDA on those features to see how they correlated with our response variables. So far, the following is the features we pick:  
* number of transactions    
* number of discount sale     
* amount of money sale  

## Week 4
This week, after some discussions and exploration of datasets, we found that the previous business questions are not that feasible, so we meet together and decided to come up with more research questions. 

Possible Question 5:    

Goal: Cross-Selling predictions? By implementing machine learning models, we can know what are some commodities that being sold together. This way, we can maximize our selling profits by providing bundle service or cross-selling services, and provide discount accordingly.     
 
Possible Question 4:

Goal: Identify key characteristics of customers. This can be done with clustering techniques to group customer by behaviors/transactions based on transaction history, purchase behavior and brand, departments. Can identify transaction amounts, preferred brands, and geographical distriubtion. This information can be used to target marketing strategies. 


Possible Question 3: 

GOAL: Predict the sale price of items in stock (SPRICE)
Relevant Attributes: Sale price, other attributes highly related to sale price(Determined through EDA and data cleaning)
  - possible other attributesL: brand, style, department etc. 
Methodologies: Linear Regression,Ridge and Lasso Regressionm,  SVM, KNN, Gradient Boosting Machines (GBM) 

## Week 3
After some basic data cleaning and we decided to do a brainstorming and research on machine learning questions we are going to work on.  

Possible Question1:    
GOAL: To predict the daily return rate of a given store.    
Metric: P/P+R P is number of SKU purchased per store per day, and R is the number of SKU returned per store per day.   
Methodologies:   
1.SARIMA: this is a preliminary model that we could first try on to get a sense of how difficult this problem will be.   
2.LSTM: this model is excellent in predicting based on both long and short memories. https://colah.github.io/posts/2015-08-Understanding-LSTMs/    
3.DeepAR: this model is good at learning seasonal behaviors and dependencies on given covariates across time series. Woth to try it out. https://docs.aws.amazon.com/sagemaker/latest/dg/deepar.html   

Possible Question2:

Can we predict customer churn for Dillard's retail chain based on their purchasing behaviors, frequency of transactions, and response to promotions, allowing the business to identify at-risk customers and implement retention strategies?

Relevant Attributes: STORE, SALEDATE, AMT

Specific Machine Learning Method: Classification Models (e.g., Logistic Regression, Decision Trees, Random Forest, Gradient Boosted Trees, Neural Networks)

Predictive:
Can we forecast the transaction frequency and amounts for the next quarter based on historical data?
Which stores are at the highest risk of seeing a drop in customer transactions in the upcoming months?

Expected Outcomes:
Time series analysis results showcasing transaction trends over time for different store locations.
Identification of specific store locations with declining transaction trends.


## Week 2
database upload:
This week we have uploaded all the datasets to the postgreSQL and tries to do load the data from the cloud to do analysis. It takes a long time to upload trnsact data (11 GB). Others takes less than 1 minute. We have also made the connection between python and Postgress to allow data to be read into a jupyter notebook. In addition, we have imported the database into Python and performed further exploratory data analysis and data cleaning.

The trnsact table comprises 120916896 observations. For our exploratory data analysis, we've randomly selected 5000 observations. Through observation, variables like REGISTER, TRANNUM, SEQ, INTERID, and MIC are internal codes used by Dillard's and may not have meaningful external use. Additionally, the extra column contains only zeros and ones, which we consider irrelevant and do not consider individually for analysis


Goals For next week:
* Figure out the machine learning topic we are going to present in dashboard.
* Data cleaning
* Do more EDA on every dataset and some data visualzation.
* figure out what variables are important for us for our machine learning problem(If we have time)? 


## Week 1
* This week our goal was to download all the files, load them into Python and begin exploring the data
* Our team also downloaded Postgres 

Findings

Skuinfo.csv
* This table contains 13 columns named 'SKU', 'DEPT', 'CLASSID', 'UPC', 'STYLE', 'COLOR', 'SIZE', 'PACKSIZE', 'VENDOR', 'BRAND', 'Unknown1', 'Unknown2', 'Unknown3']
* The column types are all strings 
* Missing values: 
* Color is missing one row 
* For Unknown 1, it seems to contain some information about brand, so we decided to keep it for further investigation.
* Unknown 2 and unknown 3 are missing 1556030 and 1564158 respectively
* Because Unknown 2,3 are missing 99% of the values and also only contains values 0 and 1, so we decided to drop it. 
* The total number of rows is: 1564178

Strinfo.csv
* The table contains 4 columns: ‘City’, ‘State’, ‘Zip’, ‘unknown’
* we Dropped unknown column bc first it only has 0 and 1, second it is not in the schema.
* City and State are of type string
* Zip is of type integer 
* There are no missing values in this table 
* There are 453 rows in this table 
* There is no Depluates for store information. 

Deptinfo.csv
* There are 3 columns: 'Dept', 'DeptDESC', 'unknown'
* We dropped the unknown column the same reason above.
* Dept is of type integer
* DeptDESC is of type string 
* There are 60 rows in this table 
* it  has no duplicates. 

skstinfo.csv
* The table contains 5 columns, which are ['SKU', "Store", "Cost", "Retail", "unknown"]
* We dropped the unknwon for the same reason above.
* besides we found that there are about half of the SKU whose COST is HIGHER than Retail, we may want to know which SKU it is.  


Goal for Next Week:
* More EDA for each table
* Come up with data cleaning strategies for each table 
* Begin implementing data cleaning strategies 
* Connect to NU Postgress

