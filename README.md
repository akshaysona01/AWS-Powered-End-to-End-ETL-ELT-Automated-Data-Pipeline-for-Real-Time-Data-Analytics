# AWS-Powered-End-to-End-ETL-ELT-Automated-Data-Pipeline-for-Real-Time-Data-Analytics

## Project Overview
This project was developed for CarePlus, a healthcare support company that generates large volumes of system logs and customer support tickets daily. Managing and analyzing this raw data manually was inefficient and error-prone. To solve this, we designed an end-to-end data pipeline using AWS services. The pipeline collects raw data from logs and tickets, stores it securely in S3, processes and cleans it with AWS Glue, and makes it queryable using Athena. Finally, insights are visualized in Power BI dashboards, helping CarePlus improve customer service efficiency, issue resolution times, and overall decision-making. This project demonstrates an end-to-end ETL/ELT data pipeline architecture built on AWS, designed to automate data ingestion, transformation, and visualization from Amazon S3 to Power BI. The solution enables automated, scalable, serverless, and cost-efficient data processing for business intelligence reporting and analytics.

## Live Dashboard:
https://app.powerbi.com/view?r=eyJrIjoiNGE1MzRjN2YtMzAwYy00YWJmLWE0OTAtYzM3YzIxNDFmYzY4IiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9

## Presentation:
https://www.canva.com/design/DAG0h0V4MDY/WoBa6XU63b9sNvZj2u7yCQ/view?utm_content=DAG0h0V4MDY&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=h48701fd178

## Video Presentation:
https://youtu.be/hSt7Orcy54Q

## Architecture Overview
<img width="12599" height="3510" alt="png3xwoembed" src="https://github.com/user-attachments/assets/20d23a70-fa88-41b7-9586-2bfe102eabac" />



### Data Flow:
**Source Data → Amazon S3 → AWS Lambda → AWS Glue → Amazon Redshift → Power BI**

## Key Steps:
### Data Ingestion (S3):
<img width="2553" height="905" alt="s3_buckets" src="https://github.com/user-attachments/assets/386e6b8d-c324-4f55-93dd-386d79240f97" />
<img width="2538" height="910" alt="trigger_events_s3" src="https://github.com/user-attachments/assets/a7ab5dd3-107c-4d14-beed-7c1ca459352d" />
Designed an Amazon S3 data lake architecture with dedicated raw (CSV/JSON/Log) and processed folders to manage data across ETL/ELT stages, converting raw files into optimized Parquet format for efficient querying and storage.
Ingested raw source files into the S3 raw zone, then stored cleansed and transformed outputs in the processed zone post ETL job execution.
Implemented lifecycle policies and versioning in S3 to optimize storage costs, maintain data integrity, and ensure traceability across pipeline runs.
<img width="2550" height="912" alt="iam_roles" src="https://github.com/user-attachments/assets/196f4380-fd8e-4452-a6f9-301f02e03d45" />




### Data Transformation (Glue + Lambda):
<img width="2550" height="919" alt="lambda_functions" src="https://github.com/user-attachments/assets/77cd7758-13aa-48bf-9e7c-0b333086b1ee" />
AWS Glue performs data cleaning, deduplication, and schema alignment using PySpark.
Developed AWS Lambda functions to automate ETL/ELT workflows, triggering AWS Glue jobs for data transformation and loading into Redshift.
<img width="2539" height="914" alt="glue_etl_visual" src="https://github.com/user-attachments/assets/08cc80b6-3dce-4aa0-8c67-76a1f572c213" />
<img width="2536" height="911" alt="glue-etl-jobs" src="https://github.com/user-attachments/assets/7f9f0bc0-0098-4732-87f4-2d9809ac8a21" />
Configured S3 event triggers and SNS notifications to automatically trigger Lambda functions when new data files were uploaded, enabling real-time pipeline execution.
Implemented serverless orchestration using Lambda to manage ETL task scheduling, error handling, and pipeline monitoring for improved reliability.



### Ad-Hoc Analysis (AWS Athena):
<img width="2551" height="925" alt="athena_ad_hoc_analysis" src="https://github.com/user-attachments/assets/5276080f-04b8-456b-acbe-b5f30f7d0dc6" />
Utilized AWS Athena for ad-hoc querying and analysis directly on S3 processed data, eliminating the need for data movement.
Created SQL-based interactive queries in Athena to validate ETL outputs and perform quick data quality checks.
Improved analytical efficiency by reducing query response time and enabling on-demand data exploration over large datasets.



### Data Loading (Redshift):
<img width="2554" height="911" alt="redshift_query" src="https://github.com/user-attachments/assets/56655e94-ead2-4a82-b0ab-3e13a029e902" />
<img width="2546" height="913" alt="redshift_database" src="https://github.com/user-attachments/assets/1b5c0bf8-f1c1-4cbb-b400-836e2b5c1658" />
Configured Amazon Redshift as a centralized data warehouse to store and analyze transformed data for business intelligence reporting.



### Data Visualization (Power BI):
<img width="1668" height="818" alt="support_tickets_power_bi" src="https://github.com/user-attachments/assets/4a9831e3-09f8-4cc9-b0b4-9a4a9b0539cb" />
<img width="1423" height="790" alt="support_logs_power_bi" src="https://github.com/user-attachments/assets/78853196-e7e2-464b-b468-cc7f1aec1454" />
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
