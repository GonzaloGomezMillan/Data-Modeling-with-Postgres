# **DATA MODELLING WITH POSTGRES**

## **Introduction**
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Your role is to create a database schema and ETL pipeline for this analysis. You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.

## **Files description**
- **sql_queries.py**: In this file you can find all the necessary sql queries to run the code etl.py and etl.ipynb. That includes queries to initially drop the tables if they have been previously created, to create the tables defining all the features and their correspondent datatypes and to insert the values into each of those tables.
- **create_tables.py**: This file uses the sql_queries.py and some defining functions to create the tables commented in the description of sql_queries.py.
- **etl.ipynb** : Jupyter Notebook file to check that the ETL code works only for part of data and that has been the base of the code included in the etl.py file.
- **test.ipynb**: This is a file to check if some of the most common mistakes by of this project has been avoided. 
- **etl.py**: Python file which carry out the whole ETL process.
---

## **Interaction with the project**
- First it is necessary to run create_tables.py. After that please run "etl.py", so the ETL process of the files takes place.

 ---

## **Database schema design and ETL pipeline**
***Fact tables***
1. **songplays**: records in log data associated with song plays i.e. records with page NextSong
    - *songplay_id* - SERIAL PRIMARY KEY
    - *start_time* - BIGINT 
    - *user_id* - int 
    - *level* - varchar
    - *song_id* - varchar
    - *artist_id* - varchar
    - *session_id* - int
    - *location* - varchar
    - *user_agent* - varchar

***Dimension tables***

2. **users**: users in the app
    - *user_id* - int PRIMARY KEY
    - *first_name* - varchar 
    - *last_name* - varchar 
    - *gender* - varchar
    - *level* - varchar

3. **songs**: songs in music database
    - *song_id* - varchar PRIMARY KEY
    - *title* - varchar 
    - *artist_id* - varchar 
    - *year* - int
    - *duration* - float 

4. **artists**: artists in music database
    - *artist_id* - varchar PRIMARY KEY,
    - *name* - varchar
    - *location* - varchar
    - *latitude* - double precision
    - *longitude* - double precision

5. **time**: timestamps of records in *songplays* broken down into specific units
    - *start_time* timestamp PRIMARY KEY,
    - *hour* - int
    - *day* - int
    - *week* - int
    - *month* - int
    - *year* - int
    - *weekday* - int
---
## **Licensing, Authors, Acknowledgements, etc.**
- **Author**: The author of this analysis is Gonzalo Gomez Millan
- **Acknowledgment**: Also noteworthy is the work of **Udacity** in promoting the performance of this analysis as one of the projects in order to pass the Data Engineering Nanodegree Program.

**Acknowledgments**: 
- I wanted to thank **Kaggle** for sharing the dataset that led to this analysis.
- Also noteworthy is the work of **Udacity** in promoting the performance of this analysis as one of the projects in order to pass the Data Scientist Nanodegree.