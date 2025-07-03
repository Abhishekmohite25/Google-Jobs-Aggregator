# Google LIVE Jobs Aggregator  

## Overview:  

This project implements a complete data engineering solution that:  

- Extracts job postings data from Google Search via SerpApi
- Processes data through a medallion architecture (Bronze → Silver → Gold)
- Provides business intelligence through KPI dashboards
- Runs automated workflows for continuous data updates  

## Architecture:  

The project follows the Medallion Architecture pattern with three distinct layers:  

Data Source → Bronze Layer → Silver Layer → Gold Layer → Analytics & Reporting  
  
  
![Image](https://github.com/Abhishekmohite25/Google-Jobs-Aggregator/blob/f0532c84a87a8ee9b4f2973546c465cff8da3f43/Images/google_jobs_architecture.png)  
  
  
## Data Flow:  

1. Data Ingestion: Raw job data extracted from SerpApi
2. Bronze Layer: Raw data storage in Delta format
3. Silver Layer: Cleaned and structured data
4. Gold Layer: Business-ready data with KPIs
5. Analytics: Visualization and reporting  

  
## Technologies Used:  
  
- Data Source: SerpApi (Google Search API)
- Programming Language: Python
- Data Processing: PySpark
- Storage: Delta Lake
- Platform: Databricks
- Workflow Orchestration: Databricks Workflows
- Visualization: Matplotlib, Databricks Dashboards
- Libraries: Python Requests Library  
  

## Data Pipeline:  

### Bronze Layer (Raw Data Ingestion)  
  
Purpose: Ingest raw job data from SerpApi  
Process:  
- Initialize SparkSession
- Configure API_KEY for SerpApi
- Execute loop over job roles for specified locations
- Send GET requests to fetch data with parameters
- Store responses in JSON format
- Create DataFrame from JSON data
- Persist DataFrame in Delta table format

  
### Silver Layer (Data Cleaning & Structuring)  

Purpose: Clean and standardize the raw data
Process:  
- Initialize SparkSession
- Read data from Bronze Delta table
- Clean and structure DataFrame:
  - Remove records with missing critical fields (title, company_name, location)
  - Standardize company names (trim whitespace, apply uppercase)
  - Filter out records with null posting dates
-Store cleaned DataFrame in Silver Delta table
  
  
### Gold Layer (Business Intelligence Ready)  

Purpose: Create business-ready datasets and KPIs
Process:
- Initialize SparkSession
- Read data from Silver Delta table
- Generate Key Performance Indicators:
  - KPI 1: Top Companies by job postings
  - KPI 2: Job distribution by cities
- Store aggregated data for reporting purposes


## Automation  
### Workflow Features  
- Scheduled Execution: Automated daily pipeline runs
- Task Dependencies: Proper sequencing of Bronze → Silver → Gold layers
- Error Handling: Robust error management and recovery
- Monitoring: Built-in logging and alerting capabilities

  
![Image](https://github.com/Abhishekmohite25/Google-Jobs-Aggregator/blob/bc57d7f63870fbebf6e486d6c9585cb9a716acb3/Images/Google_Jobs_Aggregator_WorkFlow.png)  

  


![Image](https://github.com/Abhishekmohite25/Google-Jobs-Aggregator/blob/d8c044079a928466ff7e642a7ce4bbe9770005d2/Images/Dashboard1.png)  




![Image](https://github.com/Abhishekmohite25/Google-Jobs-Aggregator/blob/d8c044079a928466ff7e642a7ce4bbe9770005d2/Images/Dashboard2.png)  
