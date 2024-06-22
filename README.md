# Final Project Data Warehouse - Dibimbing - Kelompok 2

## Objectives
The challenge for you is to build a data infrastructure using synthetic data. You will be provided with a project template to assist you in your role as a Data Engineer. Here are the tasks:
- Participants should implement learned materials through an end-to-end project.
- Participants should construct a data infrastructure using synthetic data.

## Expected Output
1. Build ETL/ELT Jobs using Apache Airflow.
2. Perform Data Modeling in Postgres.
3. Create Dashboards for Data Visualization.
4. Construct a Presentation summarizing the work done.
_Note: All data used is synthetic, reflecting real-world data from an online retail company._

## Overview
### Full Pipeline
[![data-diagram.jpg](https://i.postimg.cc/HL2Y0VGT/data-diagram.jpg)](https://postimg.cc/zLyY8DXQ)

## Setup
- Customize the `.env` file with connections to the Neon Console.
- Build Docker containers using the command `make build`.
- Spin up containers using `make spinup`.
- Once all the containers ready, follow these steps:
    - Access the Airflow on port `8081`
    - Access the Metabase on port `3001`. For the username and password, refer to the `.env` file.
    - Utilize the first Postgres container as your landing zone and the second for operational purposes.
- Run the DAGs starting from the Ingest Data DAG and proceed to Data Transformation.
- Customize your visualizations:
  * Use Metabase via port 3001 with SQL queries for visualization.
  * Alternatively, connect Tableau to Postgres using the connection from Neon Console with add connection.
- Ready to go!

### Tools
* Data Warehouse: Postgresql
* Data Visualization: Tableau
* Containerization: Docker
* Workflow Orchestration: Airflow
* Language: Python, SQL
* Lib: pandas vers 2.1.0, sqlalchemy, fastparquet, fastavro, psycopg2-binary, apache-airflow, openpyxl, xlrd

### Project structure

```
.
├── dags                                  # for airflow dags
│   ├── create_new_table_dag.py                               
│   ├── data_marts_dag.py                 
│   ├── dim_fact_table_dag.py             # dim & fact table for data marts
│   ├── main_dag.py                       # ingest the data
│   └── transform_dag.py                  # for data warehouse transformations
├── data                                  # data source
├── docker                                # for containerizations
└── scripts
│   ├── .env                                  # secret keys, environment variables
│   └── requirements.txt                      # library 
```


<details>
    
### Ingest Data DAG
[![Screen-Shot-2023-12-06-at-16-32-21.png](https://i.postimg.cc/RhnxY0Y6/Screen-Shot-2023-12-06-at-16-32-21.png)](https://postimg.cc/SYqP2mkk)
### Data Transformation with DBT - Bash
[![Screen-Shot-2023-12-06-at-16-36-06.png](https://i.postimg.cc/MHbJwLWq/Screen-Shot-2023-12-06-at-16-36-06.png)](https://postimg.cc/FkRBgDdB)
### Data Transformation with DBT - Cosmos by Astronomer
[![Screen-Shot-2023-12-06-at-16-37-23.png](https://i.postimg.cc/vTX23wYg/Screen-Shot-2023-12-06-at-16-37-23.png)](https://postimg.cc/LgYV87Z2)

</details>

### Data Lineage
[![dbt-dag.png](https://i.postimg.cc/Ss1zrZ0Q/dbt-dag.png)](https://postimg.cc/DJsZfPyR)

## Additional Transforming

## Dashboard with Tableau
* Customer Lifetime Value (CLV), Identify high-value customers and understand spending patterns. This helps in tailoring marketing strategies and improving customer retention.
* Product Performance Analysis, Highlight top-performing products and categories. Use this data to manage inventory effectively and plan product development strategies.
* Burning Rate, It measures the rate at which a company is spending its capital.

[![Clean-Shot-2023-12-06-at-14-13-54.png](https://i.postimg.cc/dVmMTpdC/Clean-Shot-2023-12-06-at-14-13-54.png)](https://postimg.cc/4Yd2D8W4)

