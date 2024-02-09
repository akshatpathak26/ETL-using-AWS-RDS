
# IPL ETL Project

This Jupyter notebook performs ETL (Extract, Transform, Load) on IPL cricket data to generate player batting statistics and Dream11 fantasy scores.

## Extract
The following data is extracted from a MySQL database hosted on AWS RDS:
- Match delivery data (`delivery` table)
- Player data (`player` table) 
- Player captain data (`player_captain` table)

The data is extracted using SQL queries and Pandas `read_sql_query`.

## Transform
The extracted data is transformed as follows:
- Merge player data with match data to associate player names
- Calculate batting aggregates - runs, balls faced, 4s, 6s 
- Calculate derived metrics - strike rate, Dream11 fantasy points
- Apply business logic for Dream11 scoring system based on runs, strike rate etc.
- Filter and order players by descending Dream11 fantasy score

The transformations leverage Pandas merging, aggregation, and custom logic.

## Load 
The final Dream11 fantasy scores dataset is loaded back into MySQL on AWS RDS using SQLAlchemy.

The Jupyter notebook provides an end-to-end demonstration of the ETL process on semi-structured IPL cricket data. The use of Pandas and SQL facilitates efficient data manipulation at scale.
