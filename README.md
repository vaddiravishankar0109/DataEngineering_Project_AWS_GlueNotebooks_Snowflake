# **DataEngineering_Project_AWS_GlueNotebooks_Snowflake**

## **Overview**
This project focuses on seamlessly integrating **AWS** and **Snowflake** for efficient data processing and analysis. The extraction process follows the approach used in [Data Engineering_Using_AWSLambda_Pandas_Crawler_Athena](https://github.com/vaddiravishankar0109/DataEngineering-Project-API-Pandas-AWS-lambda-Glue-Athena), with enhanced transformation and storage mechanisms.

---

## **Workflow Architecture**

### **Data Extraction**
- Data is retrieved from a specified **API source**.
- Extracted data is saved in an **AWS S3 bucket** in JSON format.

### **Data Transformation**
Transformation is carried out using **AWS Glue Notebooks**.
- **Key steps**:
  - JSON data from S3 is converted into a **Glue Dynamic DataFrame**.
  - Transformation is performed using **PySpark**, including the application of the **explode** function.
  - Transformed data is written back to S3 in **CSV format**.

### **Data Ingestion**
- Instead of using AWS Glue Crawler and Athena:
  - **Snowflake** with **SnowPipe** handles **auto-ingestion** once the transformed CSV file lands in the S3 bucket.

### **Data Analysis**
- Data is further processed and analyzed using **Snowflake tables**.

---

## **Architecture Flow Description**
Here’s the outline for a flow diagram based on the project's architecture:

1. **API Source → (Data Extraction)**
   - Fetch JSON data.
   - Store in AWS S3.

2. **AWS Glue Notebook → (Data Transformation)**
   - Read JSON file from S3.
   - Transform using PySpark to CSV.

3. **AWS S3 Bucket → (CSV Data)**
   - Store transformed CSV file.

4. **Snowflake Integration → (Auto-Ingestion)**
   - SnowPipe auto-ingests files from S3.

5. **Snowflake Tables → (Data Analysis)**
   - Analyze ingested data.

---

