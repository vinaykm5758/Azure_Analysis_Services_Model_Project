# Building Azure_Analysis_Model using On-PREM SQL SERVER, ADF and Azure SQL DB

**Project Details:** 
The Azure Analysis model is developed using on-prem sql server tables. for ETL, ADF has been used to extract tables and data from the on-prem sql server and load them into ADLS Gen2. From storage containers, ADF pipeline is used to load the data into Azure SQL DB. Azure Analysis model is created by using Azure SQL DB tables as source and the model is processed. Once model processing was completed, the model was connected via Excel, PowerBI, and Visual Studio for further analysis and reporting purposes

Details steps are included below for processing the data from on-prem until the reporting end

**Tables List:**

1. SalesOrderDetail
2. SalesOrderHeader
3. ProductModelProductDescription
4. ProductModel
5. ProductDescription
6. ProductCategory
7. Product
8. CustomerAddress
9. Customer
10. Address


**Step:1**
Using Self-Hosted IR, connect to the On-prem SQL Server and extract the below tables to ADLS


ADF Pipeline GIT Repo: https://github.com/vinaykm5758/On_Prem_SQL_Server_Azure_Analysis_Model/tree/Azure_Data_Factory_Pipeline
Pipeline name: PL_On_Prem_to_ADLS_Gen2


![image](https://github.com/vinaykm5758/On_Prem_SQL_Server_Azure_Analysis_Model/assets/45409524/c4703ca0-e51e-4774-a959-d157f1cfa23b)

**Step:2** Once Data has landed in storage, create a new pipeline to load the data from ADLS Gen2 to Azure SQL DB

ADF Pipeline GIT Repo: https://github.com/vinaykm5758/On_Prem_SQL_Server_Azure_Analysis_Model/tree/Azure_Data_Factory_Pipeline
Pipeline name: ADLS_Gen2_To_Azure_SQL_DB

![image](https://github.com/vinaykm5758/On_Prem_SQL_Server_Azure_Analysis_Model/assets/45409524/6955e0d5-e3cb-4dda-8864-cd3d5f74d146)

Azure SQL DB tables DDL: https://github.com/vinaykm5758/On_Prem_SQL_Server_Azure_Analysis_Model/blob/main/azure_tables.sql

**Data Validations:** 
Data has been validated from On-prem SQL Tables Vs Azure SQL Tables and record counts matched

On_Prem Counts:

![image](https://github.com/vinaykm5758/On_Prem_SQL_Server_Azure_Analysis_Model/assets/45409524/726bbe13-025a-49ae-a564-fdd91387eb78)

Azure SQL Tables Counts:

![image](https://github.com/vinaykm5758/On_Prem_SQL_Server_Azure_Analysis_Model/assets/45409524/e4e23794-c85b-429a-a9e9-fb306d0db338)


**Step: 3** Once tables are loaded, spin up Azure analysis services, using Visual Studio, connect to Azure SQL DB as data source, and extract all the required tables

![image](https://github.com/vinaykm5758/On_Prem_SQL_Server_Azure_Analysis_Model/assets/45409524/b4a32c79-1208-431c-8f5c-117134d1273c)


Once, table extractions are completed and the corresponding ER has been established for all tables, process the model by clicking Process all

**Step:4**  Go to the Analysis model, check for your model, and then click on open on Excel

Excel sheet connection to Analysis Model: https://github.com/vinaykm5758/On_Prem_SQL_Server_Azure_Analysis_Model/blob/main/Azure_Tabular_Model_Analysis_Report.xlsx

![image](https://github.com/vinaykm5758/On_Prem_SQL_Server_Azure_Analysis_Model/assets/45409524/0809d5af-b99d-4a12-9900-e3d4193b200f)


**Step:5** Connecting the Analysis Model using PowerBI Desktop

![image](https://github.com/vinaykm5758/On_Prem_SQL_Server_Azure_Analysis_Model/assets/45409524/dec7a21a-9477-46eb-a7ad-ca39b7d7543f)


Sample PowerBI Report: https://github.com/vinaykm5758/On_Prem_SQL_Server_Azure_Analysis_Model/blob/main/Sales_Analysis_Report.pbix



