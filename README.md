# MLDS400_group014

## Week 2
database upload:
This week we have uploaded all the datasets to the postgreSQL and tries to do load the data from the cloud to do analysis. It takes a long time to upload trnsact data (11 GB). Others takes less than 1 minute. We have also made the connection between python and Postgress to allow data to be read into a jupyter notebook. 


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

