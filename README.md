##Project 4: Data Lake with Apache Spark

###Project description
A music streaming startup, Sparkify, to move their data warehouse to a data lake. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

In this project, we will build an ETL pipeline that extracts data from S3, processes them using Spark, and loads the data back into S3 as a set of dimensional tables. This will allow their analytics team to continue finding insights in what songs their users are listening to.


###Database Schema
####Fact Table
  * **songplays** - records in event data associated with song plays i.e. records with page NextSong.
    songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
   
     
####Dimension Tables
  * **users** - users in the app
    user_id, first_name, last_name, gender, level
  * **songs** - songs in music database
    song_id, title, artist_id, year, duration
  * **artists** - artists in music database
    artist_id, name, location, lattitude, longitude
  * **time** - timestamps of records in songplays broken down into specific units
    start_time, hour, day, week, month, year, weekday


###ETL Pipeline
1. Read data from S3
•	Song data: s3://udacity-dend/song_data
•	Log data: s3://udacity-dend/log_data

2. Process data using spark

3. Load it back to S3
Writes them to partitioned parquet files in table directories on S3.


###Project Structure
* etl.py reads data from S3, processes that data using Spark, and writes them back to S3
* dl.cfgcontains your AWS credentials