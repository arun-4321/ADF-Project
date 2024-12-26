# Azure Data Factory (ADF) Project

## Overview
This project demonstrates the use of Azure Data Factory (ADF) to perform Extract, Transform, and Load (ETL) processes. It includes the creation of five pipelines utilizing various ADF activities and tools. The project leverages Azure Blob Storage, triggers, and linked services to streamline data integration and management workflows.

---

## Key Features
1. **Pipelines**:
   - Created five pipelines for different ETL workflows.

2. **ADF Activities Used**:
   - **Copy Data**: To copy data between different sources and destinations.
   - **Delete**: To delete data from specified locations.
   - **Get Metadata**: To retrieve metadata information about files or folders.
   - **If Condition**: To implement conditional logic in pipelines.
   - **Set Variable**: To set values for variables during pipeline execution.
   - **ForEach**: To iterate over collections for repetitive tasks.
   - **Lookup**: To retrieve data from tables or files.
   - **Execute Pipeline**: To trigger execution of other pipelines.

3. **Tools Used**:
   - **Azure Data Factory (ADF)**
   - **Azure Data Lake Storage**

4. **Triggers**:
   - Implemented **Storage Event Trigger** to initiate pipelines based on storage events.

5. **Linked Services**:
   - Created two linked services to connect:
     - Azure Data Factory with Azure Blob Storage.
     - Azure Data Factory with GitHub.

---

## Architecture
1. **Azure Data Factory**: Serves as the primary orchestrator for the ETL workflows.
2. **Azure Data Lake Storage**: Used as the storage layer for input and output data.
3. **Triggers and Linked Services**: Enable seamless connectivity and automation.

---

## Pipeline Details
### Pipeline 1: [PipelineManager]
- Description: [copy activity copies data from the  bronze layer to the silver layer, then delete activity deletes the data in the bronze layer, then followed by the Execute pipeline activity will run the pipeline2 ]
- Activities: Copy Data, Delete and Execute Pipeline

### Pipeline 2: [PipelineGit]
- Description: [This pipeline copies the data from the github using the copy activity with http connection to the silverlayer.]
- Activities: Copy Data

### Pipeline 3: [Onlyselectedfiles]
- Description: [The Data Transformation will be  performed in this pipeline on the Fact_sales1.csv file and stored in the gold layer]
- Activities: Validate, Get Metadata, Foreach, If condition, copy data, Data flow.

### Pipeline 4: [Varpipeline]
- Description: [I have used this pipeline just to know about how to use the set variable note this pipeline not used in the production.]
- Activities: , Get Metadata

### Pipeline 5: [productionpipeline]
- Description: [In this pipeline I haves used two execute pipeline activities. Included the PipelineManager and PipelineGit in execute pipeline1 and Onlyselectedfiles pipeline in the execute pipeline2 ]
- Activities: Execute Pipeline, Execute Pipeline

---

## Setup and Configuration
1. **Azure Blob Storage**:
   - Create a Data Lake Storage account.
   - Upload input data into the storage account.

2. **Azure Data Factory**:
   - Set up the Azure Data Factory instance.
   - Configure linked services:
     - Blob Storage connection.
     - GitHub connection for version control and importing data.

3. **Triggers**:
   - Configure Storage Event Trigger to automate pipeline execution based on events.

---

## How to Run the Project
1. Ensure your Azure subscription is active and you have appropriate access to Azure Data Lake Gen2 Storage and Data Factory.
2. Follow the setup and configuration steps to deploy the pipelines.
3. Trigger the pipelines manually or via the configured Storage Event Trigger.

---


## Technologies Used
- **Azure Data Factory**: For ETL orchestration.
- **Azure Blob Storage**: For data storage.
- **GitHub**: For version control and collaboration.

---

## Future Enhancements
- Add more complex workflows involving data transformation activities.
- Integrate additional data sources like Azure SQL Database, Azure Lake Database, etc.
- Implement monitoring and alerting for pipeline failures.

---

## Contact
For any questions or feedback, feel free to contact me at [arunkumar.musku@gmail.com].


