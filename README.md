# 🎧 Spotify Songs Analysis – API to Database Pipeline & SQL Analytics

##  Overview
This project demonstrates an **end-to-end Spotify data pipeline**, where song metadata is fetched using the **Spotify Web API**, stored in a **MySQL database**, and analyzed using **SQL queries** inside a Jupyter Notebook.

The focus of this project is:
- API data extraction
- Database design & ingestion
- SQL-based analysis
- Categorization and querying of music data

This is not a machine learning project. It is a **data engineering + analytics workflow**.

## 🧱 Workflow Followed
The project follows this structured flow:

1. Connect to Spotify API  
2. Extract track metadata using track URLs  
3. Store extracted data into MySQL  
4. Query and analyze stored data using SQL  
5. Categorize tracks based on popularity  

## 🛠️ Tools & Technologies Used
- **Python**
- **Spotify Web API (Spotipy)**
- **MySQL**
- **mysql-connector-python**
- **ipython-sql**
- **Jupyter Notebook**
- **SQL**

## 🔑 Spotify API Integration
- Authenticated using **Client Credentials Flow**
- Fetched track metadata using Spotify track IDs
- Extracted attributes such as:
  - Track Name
  - Artist Name
  - Album Name
  - Release Date
  - Duration (minutes)
  - Popularity score

## 🗄️ Database Setup (MySQL)
- Connected to MySQL directly from Jupyter using `%sql`
- Created a database: `spotify_db`
- Designed a table `tracks` with the following schema:

| Column Name     | Type          |
|-----------------|---------------|
| track_id        | INT (PK)      |
| Track_Name      | VARCHAR       |
| Artist_Name     | VARCHAR       |
| Album_Name      | VARCHAR       |
| Release_date    | DATE          |
| Duration_min    | FLOAT         |
| Popularity      | INT           |

- Performed operations such as:
  - `CREATE TABLE`
  - `DROP TABLE`
  - `TRUNCATE TABLE`
  - `INSERT`
  - `SELECT`

## 📥 Data Ingestion
- Read track URLs from a text file
- Extracted Spotify track IDs using **regular expressions**
- Fetched metadata for each track via API
- Inserted records into MySQL using parameterized queries
- Successfully stored **multiple tracks** into the database

## 📊 Data Exploration Using SQL
Performed SQL queries directly inside the notebook to:

- View all records in the `tracks` table
- Fetch individual tracks using `WHERE` conditions
- Analyze popularity distribution using `CASE WHEN`

### Popularity Classification Logic
sql
CASE
  WHEN Popularity >= 80 THEN 'High'
  WHEN Popularity >= 50 AND Popularity < 80 THEN 'Medium'
  ELSE 'Low'
END

Result:

High popularity tracks
Medium popularity tracks
Low popularity tracks

This helps categorize songs based on audience reach.

📈 Key Observations

Spotify popularity scores can be effectively categorized using SQL logic
API data can be reliably stored and queried using relational databases
Combining Python, SQL, and APIs enables powerful analytics workflows
Jupyter + SQL magic provides an interactive analytics environment

🧠 What I Learned

Working with third-party APIs (Spotify)

Designing relational database schemas

Inserting and querying data using SQL

Integrating Python and SQL inside Jupyter

Building end-to-end data pipelines
