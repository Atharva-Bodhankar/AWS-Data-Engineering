
## Data Engineering project AWS

In this project, we're developing an AWS-based data pipeline utilizing airflow, python, spark, and AWS services. The objective is to extract Weather Data from OpenWeather, subsequently store it in S3, and ultimately load it into Redshift using the Airflow platform. The project's high-level architecture is as follows:

![alt text](https://github.com/AnandDedha/aws-airflow-dataengineering-pipeline/blob/main/High%20Level%20Infra.drawio.png)

Building and Automating an ETL Pipeline for Weather Data

Project to build and automate an ETL pipeline to extract weather data from the Open Weather Map API, transform it using Spark, and load it into Redshift. This pipeline utilized DAGs in Airflow for task scheduling and employed a YAML-based cloud stack template to streamline the deployment and management of AWS resources.

Data Extraction and Storage

The first DAG in the pipeline handled the extraction of weather data from the Open Weather Map API. A Python operator, leveraging the "requests" library, initiated API requests and retrieved the necessary weather data. This data was then structured into a data frame and stored in an S3 bucket using the S3CreateObjectOperator.

ETL Processing and Redshift Loading

The second DAG in the pipeline focused on extracting data from S3, applying transformations, and loading the processed data into Redshift. Before proceeding, this DAG ensured that the first DAG had successfully completed its operations. The ETL processing utilized the GlueContext and Spark context to extract, transform, and load (ETL) the data. The transformed data was then loaded into the Redshift database.

Infrastructure as Code and Cloud Stack

To streamline the deployment and management of AWS resources for the data pipeline, a YAML-based cloud stack template was created. This template specified all the necessary resources, including Redshift clusters, VPCs, Glue jobs, and Mwaa environments. The use of this template significantly reduced the time and effort required to deploy and manage the data pipeline.

Conclusion

By combining DAGs in Airflow for task scheduling and a YAML-based cloud stack template for resource management, this ETL pipeline effectively extracted, transformed, and loaded weather data from the Open Weather Map API into Redshift. This approach exemplifies the benefits of automation and infrastructure as code in building and managing data pipelines.
