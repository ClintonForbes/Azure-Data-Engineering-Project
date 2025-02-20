# Azure-Data-Engineering-Project

## Project Overview
This project is all about building a complete data pipeline in Azure to address a key business need. The idea is to pull customer and sales data from an on-premises SQL database, process it in the cloud, and then create a Power BI dashboard with useful insights. The dashboard will focus on things like gender distribution and sales by product category, letting stakeholders filter and analyze data by date, product category, and gender.

## Business Requirements
The business needs to better understand customer demographics, especially gender, and how that affects purchasing behavior. The main requirements include:

1. Sales by Gender and Product Category: A dashboard that shows total products sold, total sales revenue, and a breakdown of customers by gender.  
2. Data Filtering: The ability to filter the data by gender, product category, and date.  
3. User-Friendly Interface: Stakeholders should easily be able to interact with the dashboard and make queries.  

## Solution Overview
To meet these needs, the solution is broken down into a few key parts:

### 1. Data Ingestion:
Pull data from an on-premises SQL database(SQL Server).
Use Azure Data Factory (ADF) to load that data into Azure Data Lake Storage (ADLS).

### 2. Data Transformation:
Use Azure Databricks to clean and transform the data.
Organize the data into three layers (Bronze for raw data, Silver for cleansed data, and Gold for aggregated data).

### 3. Data Loading & Reporting:
Load the transformed data into Azure Synapse Analytics.
Create a Power BI dashboard that visualizes the data, helping stakeholders explore both sales and customer demographics.

### 4. Automation:
Schedule the pipeline to run daily so the data and reports are always up-to-date.

### Technology Stack

- Azure Data Factory (ADF): To manage the data movement and transformation.  
- Azure Data Lake Storage (ADLS): For storing both raw and processed data.  
- Azure Databricks: For cleaning and transforming data.  
- Azure Synapse Analytics: For data warehousing and SQL analytics.  
- Power BI: For visualizing the data and creating reports.  
- Azure Key Vault: For secure management of credentials.  
- SQL Server (On-Premises): The source of the customer and sales data.  

# Setup Instructions

### Step 1: Azure Environment Setup

   Create Resource Group: Start by setting up a new resource group in Azure.  
   Provision Services:
      Create an Azure Data Factory instance.
      Set up Azure Data Lake Storage with containers for bronze, silver, and gold layers.
      Set up Azure Databricks and Synapse Analytics workspaces.
      Configure Azure Key Vault for managing secrets.

### Step 2: Data Ingestion

   Set Up SQL Server: Install SQL Server and SQL Server Management Studio (SSMS). Then restore the AdventureWorks database.
   Ingest Data with ADF: Use ADF to create pipelines that copy data from SQL Server to the bronze layer in ADLS.

### Step 3: Data Transformation

   Mount Data Lake in Databricks: Configure Databricks to access your ADLS data.
   Transform Data: Clean and aggregate the data in Databricks notebooks, moving it from the bronze to silver, and then to the gold layer.

### Step 4: Data Loading & Reporting

   Load Data into Synapse: Set up a Synapse SQL pool and load the gold data for analysis.
   Create Power BI Dashboard: Connect Power BI to Synapse and design visualizations based on the business needs.

### Step 5: Automation & Monitoring
   Schedule Pipelines: Set up ADF to run the data pipelines daily.
   Monitor Pipeline Runs: Use the monitoring tools in ADF and Synapse to ensure everything runs smoothly.
   
## Conclusion
This project provides a solid, automated end-to-end solution for analyzing customer demographics and their impact on sales. The data pipeline ensures that stakeholders always have access to the freshest insights, making it easier to make data-driven decisions.

#### Acknowledgements
Credit to [Luke](https://www.youtube.com/watch?v=ygJ11fzq_ik&t=3472s).
