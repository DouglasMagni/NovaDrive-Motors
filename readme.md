# Sales Data Pipeline Project

This project is a guided exploration into modern data engineering and analytics tools, including PostgreSQL, Apache Airflow, Snowflake, and dbt.

## Project Scope

1. **Connect and Explore the Sales Database:**
   - Utilized PostgreSQL for exploratory data analysis of sales data.

2. **Configure Airflow:**
   - Set up an AWS EC2 instance to run Airflow.
   - Installed Docker on the virtual machine to manage the Airflow containers.

3. **Set Up Snowflake:**
   - Created databases, schemas, warehouses, and tables in Snowflake.

4. **Create a Data Pipeline with Airflow:**
   - Built a data pipeline using Python.
   - Created and published a DAG in Airflow to transfer data from PostgreSQL to Snowflake.
   - Tested data loading and explored the data in Snowflake.

5. **Build and Configure the Analytical Layer with dbt:**
   - Created various models and tests.
   - Ran jobs to transform data and explored the results in Snowflake.

## Project Architecture

- **PostgreSQL Database:** Sales data ingested every minute, handled in batches for operational processing.
- **Apache Airflow:** Managed the data pipeline (ELT) using Python. Hosted on an AWS EC2 instance with Ubuntu, using Docker to deploy Airflow.
- **Snowflake Data Warehouse:** Received transformed data from the operational layer for analytical processing.
- **Staging Database:** Acted as an intermediate storage, receiving new records from Airflow.
- **dbt (Data Build Tool):** Transformed data from the staging database into the analytical layer for business insights.

## Business Questions Answered

- Sales by dealership
- Sales by vehicle
- Sales by salesperson
- Temporal sales trends

## Screenshots

### dbt Models
![dbt Example](./screenshots/dbt_example.png)

### Snowflake Data
![Snowflake Example](./screenshots/snowflake_example.png)

### Airflow DAG
![Airflow Example](./screenshots/airflow_example.png)

## Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/your_username/your_repo_name.git
   cd your_repo_name
