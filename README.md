# MLDS400_group014

## Week 1
* This week our goal was to download all the files, load them into Python and begin exploring the data
* Our team also downloaded Postgres 

Findings

Skuinfo.csv
* This table contains 13 columns named 'SKU', 'DEPT', 'CLASSID', 'UPC', 'STYLE', 'COLOR', 'SIZE', 'PACKSIZE', 'VENDOR', 'BRAND', 'Unknown1', 'Unknown2', 'Unknown3']
* The column types are all strings 
* Missing values: 
* Color is missing one row 
* Unknown 2 and unknown 3 are missing 1556030 and 1564158 respectively 
* The total number of rows is: 1564178

Strinfo.csv
* The table contains 4 columns: ‘City’, ‘State’, ‘Zip’, ‘unknown’
* City and State are of type string
* Zip is of type integer 
* There are no missing values in this table 
* There are 453 rows in this table 

Deptinfo.csv
* There are 3 columns: 'Dept', 'DeptDESC', 'unknown'
* Dept is of type integer
* DeptDESC is of type string 
* There are 60 rows in this table 


Goal for Next Week:
* Come up with data cleaning strategies for each table 
* Begin implementing data cleaning strategies 
* Connect to NU Postgress
