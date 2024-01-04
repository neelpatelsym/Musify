# Musify

An extensive data engineering initiative involving Kafka, Spark Streaming, dbt, Docker, Airflow, Terraform, GCP, and various other components is underway.

## Description

### Objective

The initiative involves establishing a data pipeline that captures real-time events from a simulated music streaming service, akin to platforms like Spotify. The incoming data includes events such as user song plays, website navigation, and authentication activities. This real-time data is processed and periodically stored in the data lake every two minutes. Subsequently, an hourly batch job processes this stored data, applies necessary transformations, and generates tables for our dashboard to produce analytics. The batch process will generate facts and dimension tables in form of star schema in Big Query Data Warehouse. The focus of the analysis will be on metrics such as popular songs, active users, and user demographics.

### Dataset

[Eventsim](https://github.com/Interana/eventsim) is a tool designed to produce event data that simulates page requests for a fictitious music website, creating results that closely resemble authentic user data while being entirely fictional. The Docker image utilized is sourced from [viirya's fork](https://github.com/viirya/eventsim).

Eventsim generates events using song data from the [Million Songs Dataset](http://millionsongdataset.com) and in this instance, a [subset](http://millionsongdataset.com/pages/getting-dataset/#subset) of 10,000 songs has been employed.

### Tools & Technologies

- Cloud - [**Google Cloud Platform**](https://cloud.google.com)
- Infrastructure as Code software - [**Terraform**](https://www.terraform.io)
- Containerization - [**Docker**](https://www.docker.com), [**Docker Compose**](https://docs.docker.com/compose/)
- Stream Processing - [**Kafka**](https://kafka.apache.org), [**Spark Streaming**](https://spark.apache.org/docs/latest/streaming-programming-guide.html)
- Orchestration - [**Airflow**](https://airflow.apache.org)
- Transformation - [**dbt**](https://www.getdbt.com)
- Data Lake - [**Google Cloud Storage**](https://cloud.google.com/storage)
- Data Warehouse - [**BigQuery**](https://cloud.google.com/bigquery)
- Data Visualization - [**Data Studio**](https://datastudio.google.com/overview)
- Language - [**Python**](https://www.python.org)

### Architecture

![musify-architecture](images/Musify-Architecture.jpg)

### Final Result

![dashboard](images/dashboard.png)
## Setup

**WARNING: You will be charged for all the infra setup. You can avail 300$ in credit by creating a new account on GCP.**
### Pre-requisites

If you already have a Google Cloud account and a working terraform setup, you can skip the pre-requisite steps.

- Google Cloud Platform. 
  - [GCP Account and Access Setup](setup/gcp.md)
  - [gcloud alternate installation method - Windows](https://github.com/DataTalksClub/data-engineering-zoomcamp/blob/main/week_1_basics_n_setup/1_terraform_gcp/windows.md#google-cloud-sdk)
- Terraform
  - [Setup Terraform](https://github.com/DataTalksClub/data-engineering-zoomcamp/blob/main/week_1_basics_n_setup/1_terraform_gcp/windows.md#terraform)
