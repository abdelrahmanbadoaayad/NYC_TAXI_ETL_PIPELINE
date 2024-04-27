# NYC_TAXI_ETL
 this project is about making etl pipeline on nyc taxi from scratch to power bi
NYC_TAXI_ETL Project Overview:-
this project is about making etl pipeline on nyc taxi from scratch to power bi , it provides one place to data driven decision making.

Project Architecture :-
the architecture of this project built on on-premises data-warehouse  which contains 4 main stages (i will illustrate the bellow steps in details) :-
1- Extract (sources of the project are mainly csv files from NYC_TAXI TRIPS WEBSITE , i got files from 2017 to 2020 and i will search for files before that)
2- Transform (transformation steps are mainly focus on uploading data in the final stage to be (valid, acceptable-quality)
3- Load (after the initiate transformation data will be loaded to MySQL database as the data-warehouse of the project)
4- Serve (then i will make ad-hocs and connect the data-warehouse with power bi to get informative insights)

Technologies Used :-
1- jupyter notebook (python programming language)
2- MySQL database
4- power bi

project steps in details :-

-the extract process begins with getting the csv files from the data source (site) through downloading it into a specific folder (retention :- yearly and it will be daily),
-in the transform process (it take the main time and resources of the project and it all written in python code) i begin with creating python script file called "nyc_taxi_etl_pipeline"
and i imported all libraries used in the project, I made data quality checks function on the source files (i wrote a code get me # of rows ,columns, columns with null values and its count) then i created a function to extract (duplicated , incorrect dates and the columns with null values) then i extracted these data quality issues into csv files named with its issue type and date of creation , then i uploaded these data quality issues to data quality table (in enterprise i will send these data to the concerned department to revise the quality root cause and solve it).
now i have a good quality source files ,iadded more columns for pickup & dropoff datetime ,then i split these files into chunks (made a function to group the data frame with the year and month of the source file name as if the file name called 2017 it will split this file into 12 files each one named 1-2017-processing-data.csv ,2-2017-processing-data.csv and etc.)
-in the load step i created schema called nyc_etl and it contains tables about dimensions, fact and data quality tables , then i made a function to load data quality issues files (mentioned it before) and another function to load the chunked files to the data warehouse then rename it and move it to another repository .
-in the serving layer i connect the data warehouse to power bi application in order to get some insights and analysis of the data we have.

last but not least this project is v1 ,i will add some features on the project to be more automated such as running the code via orchestration tool such as (airflow) to orchestrate the code and send me notifications to easily monitor the full process. 
