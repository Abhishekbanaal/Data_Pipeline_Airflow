Sparkify, a streaming service for music, has decided that it is time to increase automation and monitoring of its data warehouse ETL pipelines and has determined that Apache Airflow is the appropriate technology to do so. They have made the decision to build dynamic, reusable task-based high-grade data pipelines that can be easily backfilled and monitored. In order to detect any differences in the datasets, they wish to run tests against their datasets once the ETL procedures have been completed. They have also highlighted that the data quality plays a significant role when analysis are performed on top of the data warehouse.

The source data resides in S3 and needs to be processed in Sparkify's data warehouse in Amazon Redshift. The source datasets consist of CSV logs that tell about user activity in the application and JSON metadata about the songs the users listen to.

# Project Structure

## DAG

1. sparkify_dag.py: Directed Acyclic Graph definition with imports, tasks and task dependencies
2. sparkify_udacity_dag: SubDag responsible for loading Dimensional tables tasks

## Operators and Helpers

1. sql_queries: Contains SQL Table creations statements
2. table_creation: Creates Staging, Fact and Dimentional tables
3. redshift_staging: Copies data from S3 buckets into redshift staging tables
4. dimension_loading: Loads data from redshift staging tables into dimensional tables
5. fact_loading: Loads data from redshift staging tables into fact table
6. data_quality: Validates data quality in redshift tables
