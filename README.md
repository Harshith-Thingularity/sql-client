#Apache Flink SQL Example with CSV Data
## Description
This project demonstrates how to set up and run an **Apache Flink SQL** job to read data from a CSV file, process the data, and perform basic SQL operations like **insertions** and **queries**. This example uses a **local CSV file** for simplicity.
## Prerequisites
- **Apache Flink** (version 2.0.0 or later)
- **Java 8 or later**
## Setup Instructions

1. Download and Install Apache Flink:
   - [Apache Flink Downloads](https://flink.apache.org/downloads.html)
   - Extract the Flink binary and navigate to the extracted folder.
   - Start the Flink cluster:
     ```bash
     ./bin/start-cluster.sh
     ```

2. Create a CSV file named `people.csv`:
   ```csv
   name,age,city
   John,25,New York
   Jane,30,Los Angeles
   Mike,35,Chicago
## after starting the cluster write this code
  ```
  CREATE TABLE people (
  name STRING,
  age STRING,
  city STRING
) WITH (
  'connector' = 'filesystem',
  'path' = 'file:///path/to/your/people.csv',
  'format' = 'csv',
  'csv.ignore-first-line' = 'true'
);
 ```
## query the data
 ```
SELECT * FROM people;
 ```

## To insert new data
 ```
INSERT INTO people (name, age, city) VALUES ('Alice', 28, 'Boston');
 ```

