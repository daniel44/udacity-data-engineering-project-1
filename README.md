### Sparkify Music Streaming Database & ETL

##### Purpose and goals of the database
The database will enable Sparkify to analyze the songs and user activity data through diverse Data Analysis techniques, with the end goal of understanding user patterns and tailoring the product to meet the market needs. It will serve as the underlying database for any analysis conducted across the company related to user streaming activities

##### Database schema design
The database was designed with a Star schema, which enables high-speed analytic queries at a low resource cost. Due to the nature of the data and end goal, it was decided to utilize a RDBMS - PostgresDB. The database design is as follows:

###### Fact table
1. Songplay

###### Dimension tables
1. Songs
2. Artists
3. Users
4. Time

The tables described above will capture the information collected (Please refer to secion Data pipeline for further details) and expose it through PostgresDB.

##### Data pipeline

###### Source data
The data is sourced is from two different datasets:

1. A set of JSON files that include general information about a song and its corresponding artist. The files are partitioned by the first three letters of each song's track ID. 
2. A set of JSON files that include activity logs from the Sparkify app.

Both datasets are stored within Sparkify servers

###### Database creation and constraints

A PostgresDB database was created with the tables described above, and primary and foreign keys were assigned. In addition not null constraints were applied where needed. The tables were created using the SQL included in sql_queries.py and executed through the create_tables.py script.

###### ETL pipeline

The data pipeline include the following steps:

1. Read both datasets from the source through a python script
2. Load the song data in pandas dataframes
3. Categorize each data point in the song data and split it across the corresponding tables defined in the schema
4. Insert the data in the corresponding tables within the database
5. Load the logs data in pandas dataframe, categorize the data and insert within the postgres database

The ETL script is executed through the etl.py file

##### Analysis and Data Quality results

The file test.ipynb provides queries to review that the load of the data is accurate. For instance, a "%sql SELECT * FROM songs LIMIT 10;" is reflected as follows:

![Songs Dataset](/docs/songs.png)
