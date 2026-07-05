# DuckDB Tutorial

## Installation

```bash
curl https://install.duckdb.org | sh
```

## Getting Started

Create a weather database.

```bash
duckdb weather.db
```

Create 2 tables.

```sql
CREATE TABLE weather (
    city    VARCHAR,
    temp_lo INTEGER, -- minimum temperature on a day
    temp_hi INTEGER, -- maximum temperature on a day
    prcp    FLOAT, -- precipitation (น้ำในบรรยากาศที่ควบแน่นและตกลงมาสู่พื้นโลก)
    date    DATE
);

CREATE TABLE cities (
    name VARCHAR,
    lat  DECIMAL,
    lon  DECIMAL
);
```

Load data to tables from the CSV files.

```sql
COPY weather FROM 'weather.csv'
COPY cities FROM 'cities.csv'
```

Play with data.

```sql
SELECT * FROM weather;
SELECT city, temp_lo, temp_hi, prcp, date FROM weather;
SELECT * FROM weather WHERE city = 'San Francisco' AND prcp > 0.0;
SELECT * FROM weather ORDER BY city;
SELECT * FROM weather INNER JOIN cities ON weather.city = cities.name;
SELECT city, max(temp_lo) FROM weather GROUP BY city;
```
