# Overview
Let's assume that you are working on a data project and are responsible for building a data pipeline (ETL pipeline) to ingest CSV format files using AWS Glue, run some analytical queries using AWS Athena, and visualize the data using AWS QuickSight. We will use the CloudFormation template (IaC) to build the required infrastructure, such as the AWS Glue job, IAM role, and crawler and custom python scripts for the AWS Glue job and to upload data files from the local directory to the S3 bucket. Below is the reference architecture for our use case;

**Data Pipeline - Reference Architecture**

![alt text](images/data-pipeline-arch.png)
 

# Prerequisite
1. Change the following parameter values in **glue-etl-process.py** file
    - region: AWS REGION
    - source_file_path: ENTER YOUR S3 BUCKET PATH
    - target_file_path: ENTER YOUR S3 BUCKET PATH
    - glueCrawler_name: This name should match the name mentioned in aws-artifacts-creation.yaml file

2. Change the following parameter values in **upload-file-s3.py** file
    - local_file_path: Your local dataset file path 
    - bucket_name: S3 Bucket Name
    - s3_file: S3 Bucket Prefix(Directory structure)

3. Before running the CF template, change the following paramter values in **aws-artifacts-creation.yaml** file
    - AWSIAMRoleName
    - AWSGlueJobName:
    - AWSGlueCrawlerName:
    - AWSGlueCatalogName:
    - AWSGlueJobTriggerName:
    - GlueJobScriptLocation: Glue Job Script S3 bucket path
    - CrawlerS3Path: curated-data S3 bucket path