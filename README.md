ETL Project
-
SPAR NORD BANK ETL PROCESS AND DATA ANALYSIS
-
PROBLEM STATEMENT
Spar Nord Bank is trying to observe the withdrawal behavior and the corresponding dependent factors to optimally manage the refill frequency. Apart from this, other insights also have to be drawn from the data.

The overall task in this project will be to build a batch ETL pipeline to read transactional data from RDS, transform and load it into target dimensions and facts on Redshift Data Mart(Schema).

Please note that the source data and target schema details are provided to better understand the source and targets, which would help design the ETL pipeline. Once the data is loaded into Redshift, you would have to write the analytical queries discussed above.

We have data from more than 100 ATMs across Denmark. Data is captured for every transaction including, card type, location, date, time, ATM type, etc.

Also, the transaction amount field in the data set was added separately using a random function for the analysis purpose.

Coming to the analysis part, you will be tasked to carry out the calculations to perform the following analytical queries:

Top 10 ATMs where most transactions are in the ’inactive’ state
Number of ATM failures corresponding to the different weather conditions recorded at the time of the transactions
Top 10 ATMs with the most number of transactions throughout the year
Number of overall ATM transactions going inactive per month for each month
Top 10 ATMs with the highest total amount withdrawn throughout the year
Number of failed ATM transactions across various card types
Top 10 records with the number of transactions ordered by the ATM_number, ATM_manufacturer, location, weekend_flag and then total_transaction_count, on weekdays and on weekends throughout the year
Most active day in each ATMs from location "Vejgaard"

CURRENT OBJECTIVE
So far we have extracted the data from MySQL database using Apache Sqoop and placed it in HDFS under the path: /user/root/SRC_ATM_TRANS (Amazon EMR cluster).

Now we have to perform the following:

Read the ATM transactions data from HDFS and store it in a Spark dataframe (PySpark).
Split the dataframe into dimensions and fact dataframes with proper keys generation for each dataframe and establish relationship between them.
Store all the dimensions and fact data in the S3 bucket so that it can be loaded in Amazon Redshift and used for data analysis.
