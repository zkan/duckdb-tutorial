# DuckDB Tutorial

## Installation

```bash
curl https://install.duckdb.org | sh
```

## Getting Started

```bash
duckdb weather.db
```

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

```sql
copy weather from 'weather.csv'
copy cities from 'cities.csv'
```
