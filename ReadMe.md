# NovaDrive Motors Project

## Project Overview

This project demonstrates the implementation of a data pipeline using Apache Airflow, PostgreSQL, Snowflake, and dbt to analyze sales data. The project covers the following steps:

1. **Connect and Explore the Sales Database**: Utilized PostgreSQL for exploratory data analysis.
2. **Configure Airflow**: Set up Airflow on an AWS EC2 instance using Docker.
3. **Set Up Snowflake**: Created databases, schemas, and tables in Snowflake.
4. **Create a Data Pipeline with Airflow**: Built a data pipeline to transfer data from PostgreSQL to Snowflake.
5. **Build and Configure the Analytical Layer with dbt**: Created models, tests, and ran jobs to transform data in Snowflake.

## Architecture

- **PostgreSQL**: Sales data ingested every minute, handled in batches for operational processing.
- **Airflow**: Managed the data pipeline (ELT) using Python, hosted on an AWS EC2 instance with Docker.
- **Snowflake**: Received transformed data from the operational layer for analytical processing.
- **Staging Database**: Intermediate storage receiving new records from Airflow.
- **dbt**: Transformed data from the staging database into the analytical layer.

## Setup Instructions

### Prerequisites

- Docker
- AWS Account
- PostgreSQL Database
- Snowflake Account

### Steps

1. Clone the Repository

2. Set Up Airflow by navegating to the repository

3. Build and start the Docker containers

- run: docker-compose up --build
- Access the Airflow web server by navigating to http://localhost:8080 in your web browser. Use the default credentials (username: airflow, password: airflow) to log in.

4. Sourcing Data: Obtain a similar dataset from a public data source to reproduce the same pipeline of this project.

5. Configure PostgreSQL

- Update your Airflow connection settings in the Airflow web interface to connect to your PostgreSQL database.

6. Configure Snowflake

- Execute the SQL scripts in the sql directory to set up databases, schemas, and tables in Snowflake.
- Update your Airflow connection settings in the Airflow web interface to connect to your Snowflake account.

7. Set Up dbt

- Navigate to the dbt directory, update the profiles.yml file with your Snowflake credentials and run: dbt run

8. Create and Publish the Airflow DAG

- Ensure your postgres_to_snowflake_etl.py DAG file is located in the airflow/dags/ directory.
- Restart the Airflow web server if necessary to load the new DAG.
- Trigger the DAG from the Airflow web interface and monitor the progress.

### Screenshots

- dbt Models
  dbt.JPG

- Snowflake Data
  snowflake.jpg

- Airflow DAG
  airflow.JPG

- diagram
  diagram.JPG
