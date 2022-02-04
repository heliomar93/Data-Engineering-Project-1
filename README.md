# Sparkify
This is the first project from the Data Engineering Nanodegree. The main goal is to build a database withe the data that the team already have.

## Data
The data is divided into log data e song data. They are all in JSON.

### Log data
The log data is divided in 30 files, each one is the events from one day.
```{"artist":null,"auth":"Logged In","firstName":"Walter","gender":"M","itemInSession":0,"lastName":"Frye","length":null,"level":"free","location":"San Francisco-Oakland-Hayward, CA","method":"GET","page":"Home","registration":1540919166796.0,"sessionId":38,"song":null,"status":200,"ts":1541105830796,"userAgent":"\"Mozilla\/5.0 (Macintosh; Intel Mac OS X 10_9_4) AppleWebKit\/537.36 (KHTML, like Gecko) Chrome\/36.0.1985.143 Safari\/537.36\"","userId":"39"}```

### The song data
The song data contains the data about a song. They are splitted by the first three letters of the song ID.
```{"num_songs": 1, "artist_id": "ARD7TVE1187B99BFB1", "artist_latitude": null, "artist_longitude": null, "artist_location": "California - LA", "artist_name": "Casual", "song_id": "SOMZWCG12A8C13C480", "title": "I Didn't Mean To", "duration": 218.93179, "year": 0}```

## Files
There are 5 main files: create_tables, etl.ipynb, etl.py, sql_queries.py and test.ipynb.

### create_tables.py
The objective of this file is to create and connect to the database. Also, create and drop the tables, based on the sql_queries.py.

### etl.ipynb
This file was used to test and to prototype the code.

### etl.py
Here is the script that will process and insert the data into the database.

### sql_queries.py
All the queires are written here to create, drop the tables and to insert the data into the database.

### test.ipynb
The test file was used to test each table, to verify if the data was in the way we expected. 

## Database
After all the work of processing the data, there will be one fact table(songplays) and four dimension tables(users, songs, artists and time)

### songplays table
- start_time BIGINT,
- user_id VARCHAR,
- level VARCHAR,
- song_id VARCHAR,
- artist_id VARCHAR,
- session_id INT,
- location VARCHAR,
- user_agent VARCHAR

### users table

- user_id VARCHAR PRIMARY KEY,
- first_name VARCHAR,
- last_name VARCHAR,
- gender VARCHAR,
- level VARCHAR

### songs table

- song_id VARCHAR PRIMARY KEY,
- title VARCHAR,
- artist_id VARCHAR,
- year INT,
- duration NUMERIC

### artists table

- artist_id VARCHAR PRIMARY KEY,
- name VARCHAR,
- location VARCHAR,
- latitude NUMERIC,
- longitude NUMERIC

### time table

- start_time TIMESTAMP PRIMARY KEY,
- hour INT,
- day INT,
- week INT,
- month INT,
- year INT,
- weekday VARCHAR