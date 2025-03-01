# Health_Monitor
The Health Monitoring System is a Big Data project designed to oversee the health of microservices within a distributed architecture. It employs the Lambda architecture, integrating batch and real-time processing to monitor system resources such as CPU usage, RAM, and disk space




Health Monitoring System

Overview

The Health Monitoring System is a scalable and efficient framework designed to track and analyze the health metrics of microservices in a distributed architecture. It leverages big data technologies to process real-time and batch data, ensuring proactive monitoring and timely decision-making.

Key Features

Real-Time Health Monitoring: Continuously tracks CPU, RAM, and disk usage across microservices.

Batch and Stream Processing: Uses Hadoop MapReduce for historical analysis and Apache Spark for real-time insights.

Distributed Architecture: Supports large-scale deployment in cloud environments.

Efficient Data Storage: Stores processed data in Parquet format on HDFS for quick retrieval.

Querying with DuckDB: Enables fast and efficient querying of monitored health data.

System Architecture

The system follows the Lambda Architecture, combining batch and real-time data processing:

Data Ingestion: Microservices send health metrics via UDP to a centralized health monitor.

Processing Layer:

Batch Processing: Hadoop MapReduce processes stored health data for trend analysis.

Real-Time Processing: Apache Spark processes live data streams for instant alerts.

Storage and Querying:

Processed data is stored in HDFS as Parquet files.

DuckDB is used to run queries efficiently for reporting.

Alerting & Visualization: Generates alerts for anomalies and provides dashboards for monitoring.

Installation & Setup

Prerequisites

Java (for Hadoop and Spark)

Python (for data querying and monitoring scripts)

Hadoop & Apache Spark

DuckDB

Cloud storage (AWS S3 or HDFS)

Steps to Set Up

Install Required Packages

sudo apt-get update
sudo apt-get install openjdk-11-jdk python3 python3-pip

Set Up Hadoop & Spark

Install and configure Hadoop.

Install Apache Spark for real-time processing.

Deploy the Health Monitor

Run the microservice health data collector.

python health_monitor.py

Run Batch Processing

hadoop jar health_batch_processor.jar input/ output/

Run Real-Time Processing with Spark

spark-submit --master local[2] health_stream_processor.py

Query Processed Data with DuckDB

SELECT * FROM health_metrics WHERE cpu_usage > 80;

Usage

Monitor system resource usage in real time.

Detect anomalies and generate alerts.

Store and analyze historical performance data.

Query and visualize system health statistics.

Future Enhancements

Integration with Prometheus & Grafana for better visualization.

Support for Kubernetes monitoring.

Enhanced AI-based anomaly detection.
