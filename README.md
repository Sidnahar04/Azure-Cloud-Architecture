# CAPSTONE PROJECT – Azure Cloud Architecture

In the rapidly evolving landscape of modern technology, the advent of cloud computing has revolutionized how businesses and individuals store, access, and process data. This capstone project endeavors to deal into the intricate real of cloud architecture, aiming to design and develop an efficient, scalable, and secure infrastructure that caters to contemporary computing demands.
Our objective is to Create a scalable and secure cloud architecture for Bank Institution optimizing for performance, cost efficiency, and seamless data integration to support business growth and innovation.Here we have the industry as a Bank Institution in which we are getting some inputs from the database and we expecting some results from that.

![image](https://github.com/Sidnahar04/Azure-Cloud-Architecture/assets/68987629/1356056d-7052-415b-a00d-157c6acf69a4)

 
Here our inputs are:

**Customer data**- 
•	Customer data in banks includes personal identification details, account information, transactional behaviour, authorization details, and consent agreements.

•	This database stores data of customer. This database is a Microsoft SQL server hosted on Azure SQL.

**Location** – 
•	Geo-location data is necessary to map the IP addresses from the web server logs to the country of origin.

•	It has branch and ATM locations and it also includes the location where our customers belong. This data is in the structured format.

**Transaction data** – 
•	It includes a wide range of financial activities, including account transactions, card transactions, wire transfers, loans, ATM activities, online banking, checks, and currency exchanges.

•	This data includes details such as amounts, dates, account information, transaction types, and more. 

•	The confidentiality, integrity, and availability of this transaction data are essential for maintaining trust and security within the banking system while enabling informed decision-making and strategic planning for financial institutions.

•	This data is in the semi-structured and structured format.

**Security data** – 
•	Security data in banks encompasses information related to access logs, security alerts/incidents, firewall logs, vulnerability assessments, authentication details, compliance records, and incident response logs.

•	Maintaining the confidentiality, integrity, and availability of security data is crucial for robust security practices within banking systems.

•	This data is in semi structured format.

**Account Data** –
•	This data is essential for managing accounts, conducting transactions, providing customer service, and ensuring compliance. Safeguarding its confidentiality and accuracy is crucial for maintaining trust and security within the banking system.

•	This is a structured data stored in SQL Server or Azure SQL.


### Expected Output:- 

We have these forms of data and we would deploy it on cloud and perform some operations on those data like Machine Learning Algorithms, Azure Synapse Analytics, Stream Analytics,etc. Then we would pass the expected results to the following departments.

**Account Management team:** They would generate leads for the growth of the company using the analysis.

**Operations Team:** While following the our given Cloud architecture, certainly operations team would try to improve the processes and structure for the betterment of the company as per their goals.

**IT & Security:** This department will try to maintain or improve the security and performance as per their analysis over security data deployed over the cloud. This also includes the improvement in the performance of the website.

**Treasure & Finance:** The Treasury department manages cash flow, investments, and risks, ensuring the bank's liquidity and financial health. To improve performance, they could employ advanced analytics, streamline processes with technology, stay updated with industry trends, and optimize risk management strategies.

### Information gathering & Analysis:
•	Here we have gathered our data source, what storage we would use and the processing we would perform on the stored data. For the storage purposes, we found that Cosmos DB, Data Mart, Data Warehouse, SQL are relevant storage databases. This is the formation of the layers, bronze & Silver layer, respectively.

•	In the part of the Gold Layer, we would aggregate the data from the storage and perform some analysis using Azure Synapse Analytics, Azure Stream Analytics & Power BI.

![image](https://github.com/Sidnahar04/Azure-Cloud-Architecture/assets/68987629/a32cef75-4daf-4291-ab8b-01dc90663bb2)

We've discovered that our understanding of the cloud architecture's layer formation was incorrect. The storage layers we chose aren't cost-effective and lack the flexibility we need. We noticed a lack of proper utilization of Azure services, prompting us to rethink and redesign the architecture.

## Phase 2-Cloud Architecture :

![image](https://github.com/Sidnahar04/Azure-Cloud-Architecture/assets/68987629/c74b439e-ded6-409b-8bed-c0b10d02c836)

This represents our final architecture, where the source data is directed to the ingestion layer, generating batches. Some data flows into the Azure Event Hub while the remaining enters pipelines with triggers. From there, the data progresses into the lake house architecture, initiating layers. Initially stored in Azure Data Lake Gen 2, curated data moves to the Delta Lake forming the silver layer. Subsequent transformations occur in Synapse Analytics. Ultimately, the aggregated data is transmitted to the end-user or analysis team for further analysis, working with refined data.

### Azure Pipeline Flow based on cloud architecture:

![image](https://github.com/Sidnahar04/Azure-Cloud-Architecture/assets/68987629/437e2103-8912-40aa-acb1-f86256e8ca7f)

In this architecture, there will be pipelines dedicated to processing data to derive results used for subsequent transformations. Initially, the copy pipeline will duplicate batch and streaming data, storing it for the curation layer. Additionally, a pipeline, namely the currency converter, will facilitate global currency conversion. Further steps involve employing mapping, joins, and stored procedure pipelines, ideal for the silver layer. Finally, integration and deployment will be managed through machine learning or Azure DevOps pipelines.
