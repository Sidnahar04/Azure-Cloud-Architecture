# E-commerce Azure Cloud Architecture

## What is Cloud Architecture?
Cloud architecture refers to how various cloud technology components, such as hardware, virtual resources, software capabilities, and virtual network systems interact and connect to create cloud computing environments.
Cloud architecture coordinates component integration, allowing resource pooling, sharing, and scalable operations across networks. It's akin to an architectural blueprint for deploying applications in cloud environments.


In the rapidly evolving landscape of modern technology, the advent of cloud computing has revolutionized how businesses and individuals store, access, and process data. This capstone project endeavors to deal into the intricate real of cloud architecture, aiming to design and develop an efficient, scalable, and secure infrastructure that caters to contemporary computing demands.
Our objective is to Create a scalable and secure cloud architecture for E – commerce organization optimizing for performance, cost efficiency, and seamless data integration to support business growth and innovation. In this context, we're operating within the realm of E-commerce, where we draw data sources from a database and anticipate specific outcomes as a result.


![image](https://github.com/Sidnahar04/Azure-Cloud-Architecture/assets/68987629/d6408490-c908-4bc9-9bf7-bade8a39ae1a)


 
These are the origins of our data:

**CRM** - 
•	CRM data encompasses comprehensive consumer information, including contact details, purchase history, interactions, preferences, and feedback.

•	It's instrumental in managing customer relationships, enabling personalized communication, and providing tailored experiences based on customer behaviour and preferences.

•	Maintaining accurate and up-to-date CRM data is crucial for targeted marketing, customer retention, and improving customer satisfaction. This structured data aids in segmentation, analysing customer trends, and fostering stronger relationships between businesses and consumers.


**Inventory** – 
•	Inventory data tracks the stock of products held by a business, encompassing details such as product names, SKUs (stock keeping units), quantities on hand, locations, and statuses (available, reserved, out of stock).

•	It's pivotal for efficient supply chain management, ensuring adequate stock levels, optimizing order fulfilment, and preventing overstock or stockouts, thereby enhancing operational efficiency.

•	Maintaining accurate inventory data is crucial for reducing costs, streamlining logistics, and meeting customer demands promptly. This data is typically structured to facilitate inventory tracking, demand forecasting, and decision-making processes.


**Transactions**– 
•	E-commerce transaction data covers a wide range of online purchase activities, containing details like order IDs, product specifics, customer information, payments, and shipping details.

•	Securing this data is crucial for building customer trust and ensuring secure online transactions. It enables informed decision-making, inventory management, targeted marketing, and improved customer experiences.

•	This data, structured or semi-structured, allows for efficient analysis, trend identification, and optimization of sales strategies to meet customer needs.


**Website Traffic**:
•	Website traffic data encompasses information about the visitors to a website, including metrics like page views, unique visitors, sessions, bounce rates, sources (organic, direct, referral), and user behaviour (time spent, pages visited).

•	It's essential for understanding website performance, audience behaviour, and the effectiveness of marketing strategies. This data aids in optimizing content, improving user experience, and making informed decisions to enhance online presence.

•	Accurate website traffic data is crucial for evaluating marketing campaigns, identifying trends, and refining SEO (Search Engine Optimization) strategies. It's typically structured for analysis, enabling insights into user engagement and guiding improvements to drive website success.



### Server Layer: -  

We possess various types of data that we'll place on the cloud, utilizing tools such as Machine Learning Algorithms, Azure Synapse Analytics, Stream Analytics, among others, to conduct operations. Subsequently, we'll transmit the anticipated outcomes to the subsequent departments.

**Supply Chain Management:**  
•	Analysing data within the supply chain department revolutionizes operations by providing valuable insights into inventory, logistics, and supplier performance. These insights empower informed decision-making, driving efficient inventory management, streamlined logistics, and better anticipation of demand. 

•	This data-driven approach enhances overall efficiency, reduces costs, and enables proactive risk management by identifying and addressing potential disruptions. Continuous analysis facilitates ongoing optimization, ensuring adaptability and sustained improvements within the supply chain, ultimately leading to enhanced performance and resilience.


**Operations Team:** 
•	The operations team in e-commerce ensures smooth order fulfilment, optimizes logistics and inventory, manages the supply chain, maintains quality standards, and continually refines processes. Their coordination across departments contributes to efficient transactions, timely deliveries, quality products/services, customer satisfaction, and overall business growth. They're the backbone ensuring seamless operations and meeting customer expectations.

**IT & Security:** 
•	Analysing data across various sources equips IT & security teams in e-commerce companies to fortify cybersecurity, detect fraud, optimize system performance, ensure regulatory compliance, and enhance incident response strategies. Leveraging this data allows proactive measures against evolving threats, ensuring robust defences and continual improvement in safeguarding both the company and its customers.

**Marketing:**
•	Examining data holds immense value for the marketing team, furnishing insights that mold potent strategies. It grants a profound comprehension of customer actions, facilitating personalized campaigns through audience segmentation rooted in demographics, preferences, and buying behaviours. These insights empower marketers to efficiently distribute resources among channels, prioritizing those generating maximum engagement and conversions.


### Information gathering & Analysis:
•	We've compiled our data sources and determined our storage and processing methods. For storage, we've identified Cosmos DB, Data Mart, Data Warehouse, and SQL as suitable databases. This sets up the layers—Bronze and Silver. 
•	In the Gold Layer phase, we'll gather data from storage, conducting analysis using Azure Synapse Analytics, Azure Stream Analytics, and Power BI

![image](https://github.com/Sidnahar04/Azure-Cloud-Architecture/assets/68987629/a32cef75-4daf-4291-ab8b-01dc90663bb2)

We found that our initial comprehension of the cloud architecture's layer structure was inaccurate. The storage layers we selected aren't cost-efficient and lack the necessary flexibility. We observed underutilization of Azure services, leading us to reconsider and revamp the architecture design.

## Phase 2-Cloud Architecture :

![image](https://github.com/Sidnahar04/Azure-Cloud-Architecture/assets/68987629/c74b439e-ded6-409b-8bed-c0b10d02c836)

### Used Azure Services:

**Azure Event Hub:** Azure Event Hubs is a Big Data streaming platform and event ingestion service that can receive and process millions of events per second. Event Hubs can process and store events, data, or telemetry produced by distributed software and devices.
**Azure Stream Analytics:** Azure Stream Analytics is a fully managed, real-time analytics service designed to help you analyze and process fast moving streams of data that can be used to get insights, build reports or trigger alerts and actions.
**Azure Pipeline:** Scheduled triggers are independent of the repository and allow you to run a pipeline according to a schedule. Pipeline triggers in YAML pipelines and build completion triggers in classic build pipelines allow you to trigger one pipeline upon the completion of another.
**Azure Data Lake Storage Gen 2:** Azure Data Lake Storage is a cloud-based, enterprise data lake solution. It's engineered to store massive amounts of data in any format, and to facilitate big data analytical workloads. Azure Data Lake Storage Gen2 is a set of capabilities dedicated to big data analytics, built on Azure Blob Storage
**Azure Delta Lake:** Delta Lake is the optimized storage layer that provides the foundation for storing data and tables in the Databricks Lakehouse. Delta Lake is open-source software that extends Parquet data files with a file-based transaction log for ACID transactions and scalable metadata handling.
**Azure synapse Analytics:** Azure Synapse Analytics is a cloud-based analytics service on Azure that combines data warehousing, big data analytics, and data integration. It offers scalability, integration with various data sources, advanced analytics capabilities, and a unified workspace for efficient collaboration among data professionals.

This is our ultimate architecture setup: the source data is directed to the ingestion layer, creating batches. Part of the data goes to Azure Event Hub, while the rest enters pipelines triggered for processing. The data then moves into the lake house architecture, beginning with Azure Data Lake Gen 2. Curated data progresses to Delta Lake, forming the silver layer. Further transformations take place in Synapse Analytics. Eventually, the aggregated data is transmitted to end-users or the analysis team for deeper insights, working with refined data.

After deployment, the Azure cloud environment will feature interconnected services forming an end-to-end data processing and analytics infrastructure. Data will flow through different stages, undergo transformations, be stored, analyzed, and eventually utilized for generating insights or driving specific actions based on the architecture's design and functionality.

### Azure Pipeline Flow based on cloud architecture:

![image](https://github.com/Sidnahar04/Azure-Cloud-Architecture/assets/68987629/437e2103-8912-40aa-acb1-f86256e8ca7f)

In this architecture, there will be pipelines dedicated to processing data to derive results used for subsequent transformations. Initially, the copy pipeline will duplicate batch and streaming data, storing it for the curation layer. Additionally, a pipeline, namely the currency converter, will facilitate global currency conversion. Further steps involve employing mapping, joins, and stored procedure pipelines, ideal for the silver layer. Finally, integration and deployment will be managed through machine learning or Azure DevOps pipelines.


**Summary:**
•	Once all components are deployed on the cloud and we gather insights from Power BI dashboards and external applications, we aim to present these reports and dashboards to the organization's C-level executives. We'll highlight the efficiency gains, cost reductions, and overall advantages achieved through the Azure-based cloud architecture. 

•	This system is designed as a robust and scalable solution managing the entire data flow, ensuring streamlined operations, and enhancing customer experiences. Leveraging Azure services like Event Hubs for data intake, Data Lake Gen 2 for storage, and Synapse Analytics for data warehousing and analytics, this architecture enables real-time data processing via Stream Analytics and handles machine learning tasks using Azure Machine Learning. Azure DevOps supervises integration and deployment, establishing an all-encompassing infrastructure for efficient data management, analytics, and scalable e-commerce operations

