# Project: Data Modelling with Postgres

## Purpose of the Database
<p>The purpose of this database is to store data, that has been collected on songs and user activity, so that this data can be easily queried, to carry out analysis. <br>
Initially the data had been collected and stored in a directory of JSON log files, and as a result the data was difficult to query. <br>
An ETL pipeline was built using python and sql to extract, transform and load this data into a star schema database, with the design of the databse being optimised for query performance. <br>
This database will now allow for easier querying of data and analysis.
</p>

## Schema Design and ETL Pipeline
<p>The database follows a STAR schema, with 1 fact table (songplays) and 4 dimension tables (users songs, artists, time). <br>
**sql_queries.py** contains DROP, CREATE, INSERT AND SELECT queries <br>
**create_tables.py** uses the queries defined in **sql_queries.py** to create each of the tables in the database. <br>
**etl.py** extracts, transforms and loads data from the json files to populate the database. The json song data is processed to populate the **songs** and **artists** tables and the user activity log data is used to populatre the **time** and **users** tables. A SELECT query is then used to collect the song and artist id from the **songs** and **artists** tables respectively, and is used in conjunction with the user activity log data to populate the **songplays** table.    
</p>

## Running the Python Scripts
<p>To run the python scripts run the following commands in the terminal: <br>
**python3 create_tables.py** <br>
**python3 etl.py** <br>
</p>

<p> Alternatively, you can run the 2 cells in **run_scripts.ipyb** </p>