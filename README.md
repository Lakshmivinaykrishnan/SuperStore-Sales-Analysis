#  Super Store Sales Analysis Dashboard
### This dashboard provides an interactive visual analysis of Super Store sales data, it integrates AWS analytics services with Tableau BI to enable near real-time analysis directly from cloud data storage and processing.

## 🔧 Technologies Used
- **AWS IAM**
- **Amazon S3** (Partitioned Data)
- **AWS Glue** (Data Catalog)
- **Amazon Athena**
- **Tableau**
##  Data Pipeline & Architecture
- IAM (Identity and Access Management) 
  IAM roles and policies were created to securely grant Tableau and Glue access to S3 and Athena. Fine-grained permissions were applied to ensure least privilege access across services.

- Amazon S3
  Data is partitioned to optimize performance in Athena.

- AWS Glue
 Glue Crawler was configured to scan the S3 bucket and automatically populate the AWS Glue Data Catalog with schema information.
 A Glue Job was used to clean, normalize, and transform the raw data.


- Amazon Athena
Athena was used to query structured data directly from the S3 bucket using standard SQL.
Tables created from Glue Catalog were referenced in SQL queries for Tableau reporting.
<p align="center">
  <img src="Architecture (2).png" alt="Dashboard Preview" width="700"/>
</p>


##  Tableau Integration
Tableau Desktop was connected to Athena using the Amazon Athena ODBC Driver.
Connection required the following settings:

- AWS Region

- S3 Staging Directory

- Catalog Name: AWS Glue catalog

- Database

- Extracts were scheduled as needed to optimize performance or run live queries.
<p align="center">
  <img src="Architecture (2).png" alt="Dashboard Preview" width="700"/>
</p>
