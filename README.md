# AWS-Powered-End-to-End-ETL-ELT-Automated-Data-Pipeline-for-Real-Time-Data-Analytics

## Project Overview
This project was developed for CarePlus, a healthcare support company that generates large volumes of system logs and customer support tickets daily. Managing and analyzing this raw data manually was inefficient and error-prone. To solve this, we designed an end-to-end data pipeline using AWS services. The pipeline collects raw data from logs and tickets, stores it securely in S3, processes and cleans it with AWS Glue, and makes it queryable using Athena. Finally, insights are visualized in Power BI dashboards, helping CarePlus improve customer service efficiency, issue resolution times, and overall decision-making. This project demonstrates an end-to-end ETL/ELT data pipeline architecture built on AWS, designed to automate data ingestion, transformation, and visualization from Amazon S3 to Power BI. The solution enables automated, scalable, serverless, and cost-efficient data processing for business intelligence reporting and analytics.

## Architecture Overview
<img width="12599" height="3510" alt="png3xwoembed" src="https://github.com/user-attachments/assets/20d23a70-fa88-41b7-9586-2bfe102eabac" />

### Data Flow:
**Source Data → Amazon S3 → AWS Lambda → AWS Glue → Amazon Redshift → Power BI**

## Key Steps:
### Data Ingestion (S3):
Designed an Amazon S3 data lake architecture with dedicated raw (CSV/JSON/Log) and processed folders to manage data across ETL/ELT stages, converting raw files into optimized Parquet format for efficient querying and storage.
Ingested raw source files into the S3 raw zone, then stored cleansed and transformed outputs in the processed zone post ETL job execution.
Implemented lifecycle policies and versioning in S3 to optimize storage costs, maintain data integrity, and ensure traceability across pipeline runs.

### Data Transformation (Glue + Lambda):
AWS Glue performs data cleaning, deduplication, and schema alignment using PySpark.
Developed AWS Lambda functions to automate ETL/ELT workflows, triggering AWS Glue jobs for data transformation and loading into Redshift.
Configured S3 event triggers and SNS notifications to automatically trigger Lambda functions when new data files were uploaded, enabling real-time pipeline execution.
Implemented serverless orchestration using Lambda to manage ETL task scheduling, error handling, and pipeline monitoring for improved reliability.

### Ad-Hoc Analysis (AWS Athena):
Utilized AWS Athena for ad-hoc querying and analysis directly on S3 processed data, eliminating the need for data movement.
Created SQL-based interactive queries in Athena to validate ETL outputs and perform quick data quality checks.
Improved analytical efficiency by reducing query response time and enabling on-demand data exploration over large datasets.

### Data Loading (Redshift):
Configured Amazon Redshift as a centralized data warehouse to store and analyze transformed data for business intelligence reporting.

### Data Visualization (Power BI):
Power BI connects securely to Redshift to create interactive dashboards.
Key metrics and KPIs are visualized for decision-makers.

## AWS Services Used:

| Service             | Purpose                                        |
| ------------------- | ---------------------------------------------- |
| **Amazon S3**       | Data lake for raw and processed data storage   |
| **AWS Glue**        | ETL transformation and data catalog management |
| **AWS Lambda**      | Serverless orchestration and automation        |
| **Amazon Athena**   | Ad-hoc SQL querying over S3 data               |
| **Amazon Redshift** | Centralized data warehouse for analytics       |


## Technical Highlights
Serverless architecture: Fully managed, no EC2 required.
Automation: Lambda triggers Lambda and Glue jobs automatically upon new data uploads.
Scalability: Supports large datasets with distributed PySpark processing.
Security: IAM roles and S3 bucket policies enforce least-privilege access.
Performance: Optimized ETL workflows reduced processing time by ~30%.

## Outcomes & Impact
Automated data ingestion and transformation from multiple sources.
Reduced manual data handling time by 30%.
Improved dashboard refresh speed and analytics accuracy.
Established scalable and secure cloud-based data infrastructure.

## 👨‍💻 Author
Akshay Sonawane.
Data Analyst | AWS | SQL | Power BI | ETL Architecture
