# Black Friday Sales Data Projection | Real Time Data Streaming

## Overview

This project implements a real-time data engineering pipeline for ingesting, processing, and analyzing streaming data. The pipeline utilizes various AWS services and Python scripts to achieve end-to-end data processing and analysis capabilities.

## Architecture

The architecture of the pipeline involves the following components:

1. **Source Data Generation**: Python mock scripts generate real-time data as the source.

2. **Data Ingestion**: Boto3 library is used to ingest the generated data into DynamoDB.

3. **Change Data Capture (CDC)**: DynamoDB Streams capture any changes in the DynamoDB table.

4. **Streaming Data Processing**: EventBridge Pipe sends the DynamoDB stream records to a Kinesis stream.

5. **Data Accumulation**: Kinesis Firehose accumulates the streaming records for a certain period before processing.

6. **Data Transformation**: Lambda functions perform transformations on the accumulated records before dumping them into S3 in JSON format.

7. **Metadata Preparation**: A Glue Crawler crawls the S3 bucket to prepare metadata, enabling querying of the data using Athena.

## Setup

To set up the project, follow these steps:

1. Configure AWS credentials and permissions for the Boto3 library to access DynamoDB AWS services.

2. Deploy the Python mock scripts to generate source data.

3. Set up DynamoDB tables and streams for data ingestion and CDC.

4. Create EventBridge rules and Kinesis streams for streaming data processing.

5. Configure Kinesis Firehose delivery streams and Lambda functions for data transformation.

6. Set up a Glue Crawler to crawl the S3 bucket and prepare metadata for Athena.

## Usage

Once the project is set up, the pipeline will automatically ingest, process, and analyze streaming data in real-time. Data engineers and analysts can query the data using Athena to derive insights and make near real time data-driven decisions.
