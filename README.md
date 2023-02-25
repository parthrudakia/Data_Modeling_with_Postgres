## Data Modeling with Postgres

### Introduction

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Your role is to create a database schema and ETL pipeline for this analysis. You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.

### How To Run

First run `create_tables.py` file and then run `etl.py` file.

### Files

1. `sql_queries.py` : It has all the sql queries to create/drop tables as well as to insert data and fetch data from the tables.

2. `etl.py` : Builds the data pipeline which extracts data from the JSON files, transforms it in the way we want and loads that data into postgres database.

3. `create_tables.py`: creates database and makes an active connection with the database. Also, creates/drops tables if existed, every time it is ran.

4. `etl.ipynb` : Reads and processes a single file from song_data and log_data and loads the data into your tables. This notebook contains detailed instructions on the ETL process for each of the tables.

### Database Design and ETL Pipeline

We have chosen Star schema for our database here. Which is as following :

Fact Table: songplays
Dimensions Tables: songs, artists, users, time

The reason to choose Star Schema over Snowflake Schema is as following :

1. Easier to query without too many JOINS
2. Denormalized Tables
3. Faster aggregation

### About Data

Here, we have two main folders `songs metadata` &  `logs data`

1. `songs metadata`: collection of JSON files that describes the songs such as title, artist name, year, etc.

2. `logs data`: collection of JSON files where each file covers the users activities over a given day.



