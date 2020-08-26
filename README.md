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

###### Database creation and constraints

###### ETL pipeline

###### Data quality checks

##### Analysis results
