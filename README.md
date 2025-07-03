# Google LIVE Jobs Aggregator  

## Overview  

This project implements a complete data engineering solution that:  

- Extracts job postings data from Google Search via SerpApi
- Processes data through a medallion architecture (Bronze → Silver → Gold)
- Provides business intelligence through KPI dashboards
- Runs automated workflows for continuous data updates  

## Architecture  

The project follows the Medallion Architecture pattern with three distinct layers:  

Data Source → Bronze Layer → Silver Layer → Gold Layer → Analytics & Reporting  
![Image](https://github.com/Abhishekmohite25/Google-Jobs-Aggregator/blob/f0532c84a87a8ee9b4f2973546c465cff8da3f43/Images/google_jobs_architecture.png)  


![Image](https://github.com/Abhishekmohite25/Google-Jobs-Aggregator/blob/bc57d7f63870fbebf6e486d6c9585cb9a716acb3/Images/Google_Jobs_Aggregator_WorkFlow.png)  



![Image](https://github.com/Abhishekmohite25/Google-Jobs-Aggregator/blob/d8c044079a928466ff7e642a7ce4bbe9770005d2/Images/Dashboard1.png)  




![Image](https://github.com/Abhishekmohite25/Google-Jobs-Aggregator/blob/d8c044079a928466ff7e642a7ce4bbe9770005d2/Images/Dashboard2.png)  
