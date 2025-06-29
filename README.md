This project builds a batch pipeline that transforms raw user activity into structured behavioral insights. Data is ingested from two sources: user purchase records in CSV format and movie reviews stored in a PostgreSQL database. The pipeline extracts this data into an S3-compatible storage layer, applies sentiment classification to the reviews using a Spark ML model, and aggregates user-level metrics—such as total spending and review sentiment—using DuckDB and SQL. The final metrics are exported as a CSV file for use in dashboards and further analysis. 

The orchestration logic is managed by a DAG named user_analytics_dag, which:

1. Ingests user purchase data and movie reviews from MinIO
2. Transforms and aggregates data with Spark
3. Loads output to DuckDB
4. Renders visual reports via Quarto

Please set up the Environment using the Makefile (directories, permisions, docker container, Airflow)

The airflow UI is accessed through port 8080.

The DAG is visualized in the Airflow UI and the resulting dashboard is rendered to /dags/scripts/dashboard/dashboard.html
