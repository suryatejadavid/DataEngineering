# Customer Subscription Data Processing with AWS Glue

## Overview

This project implements a data processing pipeline using AWS Glue and PySpark to handle customer subscription data. The pipeline is designed to manage both batch and incremental data ingestion. Utilizing AWS services such as S3 and Glue, the system processes raw customer data from CSV files and transforms it for analysis. This solution facilitates efficient data handling, ensuring data is prepared for further analysis and reporting.

## Features

- **Batch Data Processing:** Handles the processing of multiple CSV files containing customer subscription data.
- **Incremental Data Processing:** Includes an incremental data ingestion mechanism, ensuring that only new or updated records are processed.
- **PySpark in AWS Glue:** Leverages PySpark in AWS Glue to transform and clean the data efficiently.
- **Storage in S3:** Data is stored in AWS S3, enabling easy access for further analysis or querying.

## Architecture

The architecture consists of the following components:

1. **S3:** Stores the raw CSV data files and processed output.
2. **AWS Glue:** Runs ETL (Extract, Transform, Load) jobs using PySpark scripts to process customer subscription data.
3. **PySpark Scripts:** Custom PySpark scripts handle data transformation and loading.

## Project Structure
customer-subscription-data-processing/
│
├── data/
│   ├── customer_subscription_2023_08_21.csv        # Raw customer subscription data
│   ├── customer_subscription_2023_08_22.csv        # Raw customer subscription data
│   └── customer_subscription_2023_08_23.csv        # Raw customer subscription data
│
├── scripts/
│   ├── pyspark_in_glue_demo.py                     # PySpark script for processing customer subscription data
│   └── incremental_data_in_glue.py                 # PySpark script for incremental data ingestion in AWS Glue
│
└── README.md                                       # Project documentation (this file)

## Prerequisites

- **AWS Account:** You need an active AWS account to use AWS Glue, S3, and other services.
- **Python 3.8+:** The PySpark scripts are written in Python.
- **AWS CLI:** For managing AWS resources and interacting with S3 and Glue.

## Setup and Deployment

1. **S3 Bucket Setup:**
   - Create an S3 bucket to store raw customer subscription data.
   - Upload the CSV files (`customer_subscription_2023_08_21.csv`, `customer_subscription_2023_08_22.csv`, and `customer_subscription_2023_08_23.csv`) into the S3 bucket.

2. **Glue Job Setup:**
   - Use the `pyspark_in_glue_demo.py` script to create a Glue ETL job that processes the raw data from the S3 bucket.
   - The Glue job will clean and transform the data, making it ready for analysis.

3. **Incremental Data Processing:**
   - Set up a Glue job using the `incremental_data_in_glue.py` script to handle incremental data ingestion.
   - The incremental job ensures that only new or updated records are processed, optimizing resource usage.

4. **Run Glue Jobs:**
   - After setting up the Glue jobs, trigger the jobs either manually via the AWS Glue console or automate the process using AWS Glue triggers.

## How It Works

1. **Batch Data Ingestion:**
   - The `pyspark_in_glue_demo.py` script processes multiple customer subscription data CSV files.
   - The processed data is written back to S3 for further analysis.

2. **Incremental Data Processing:**
   - The `incremental_data_in_glue.py` script ensures that only new data added to the CSV files is processed, avoiding duplication.

3. **Transformation:**
   - PySpark is used to transform the raw data, including cleaning, filtering, and applying any necessary transformations before saving the final dataset.

## Benefits

- **Efficiency:** Incremental data processing reduces resource consumption by only processing new or updated records.
- **Scalability:** The system is built using AWS services, ensuring it can scale according to the volume of data.
- **Automation:** AWS Glue triggers can be used to automate the data processing workflow.

## Contributing

Contributions are welcome! Feel free to submit a pull request or open an issue if you have any suggestions or improvements.


## Acknowledgments

- Developed using AWS services and PySpark.
- Special thanks to the AWS documentation and community resources.
