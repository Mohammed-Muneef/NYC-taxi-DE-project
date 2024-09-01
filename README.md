# NYC Yellow Taxi Data Engineering Project using Microsoft Fabric

## Overview

This project involves the end-to-end data engineering of NYC Yellow Taxi data for the year 2024 using Microsoft Fabric. The goal is to automate the ingestion, cleansing, and transformation of taxi trip data to generate actionable insights through Power BI reports.

## Project Architecture

The solution architecture is designed to handle monthly NYC Yellow Taxi data, storing, processing, and presenting it using Microsoft Fabric components.

1. **Data Source**:  
   - NYC Yellow Taxi data (2024) in Parquet format.
   - Static taxi zone lookup table.

2. **Landing Layer (Lakehouse)**:  
   - Store the monthly Parquet files in the Lakehouse, serving as the data storage layer.

3. **Staging Layer (Data Warehouse)**:  
   - Use Data Factory's Copy Activity to ingest data from the Lakehouse into staging tables (`stg_myctaxi_yellow` and `stg_taxi_zone_lookup`) in the Data Warehouse.

4. **Data Processing**:  
   - Apply data cleansing and transformation using Dataflow Gen2 or stored procedures.
   - Combine the cleaned taxi data with the taxi zone lookup data.

5. **Presentation Layer (Data Warehouse)**:  
   - Load the processed data into the presentation tables (`dbo.myctaxi_yellow`) for reporting purposes.

6. **Reporting Layer**:  
   - Create a semantic model on top of the presentation tables.
   - Develop dynamic Power BI reports to visualize the data.

7. **Automation**:  
   - Automate the monthly data processing using metadata tables to track processed files.
   - Ensure that staging data is deleted before loading new data and that processed data is appended to the presentation layer.

## Project Setup

### Prerequisites

- **Microsoft Fabric**: Ensure you have access to Microsoft Fabric's components like Data Factory, Dataflow Gen2, Lakehouse, and Warehouse.
- **Power BI**: Power BI for report creation.
- **Azure Subscription**: Required for accessing Fabric components and managing resources.
- **NYC Yellow Taxi Data**: Download the 2024 Yellow Taxi data in Parquet format from the NYC Taxi & Limousine Commission website.

### Steps to Run the Project

1. **Data Download**:  
   - Download the monthly NYC Yellow Taxi Parquet files for 2024.

2. **Data Ingestion**:  
   - Upload the Parquet files into the Lakehouse.
   - Use Data Factory to create a pipeline that copies data from the Lakehouse to staging tables in the Data Warehouse.

3. **Data Transformation**:  
   - Implement data cleansing and transformation logic using Dataflow Gen2 or stored procedures.
   - Combine the taxi trip data with the static taxi zone lookup table.

4. **Load Data into Presentation Layer**:  
   - Use Data Factory to load the processed data into the presentation tables.

5. **Build Power BI Reports**:  
   - Create a semantic model on top of the presentation tables.
   - Develop Power BI reports to visualize taxi trip data and generate insights.

6. **Automation**:  
   - Create and configure metadata tables to track processed files.
   - Set up an automated process to ensure each month's data is processed, with staging data cleared before new data is ingested.
