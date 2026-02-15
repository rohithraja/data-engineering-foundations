# Introduction to Big Data
what is Big Data:

A data which cannot be stored in our traditional single system like our laptops or PCs or single server where we store our data 
A data is termed as Big data if it has 
Volume : say TB or PB or data 
Variety: structured , semi-structured , unstructured data
Velocity: the speed with which the data is coming in 
Veracity: the quality/correctness of the data (we call a data is of quality if it is accurate, complete, consistent, timelinesss and fits the purpose .i.e business requirement ) 
Value: are we able to generate value out of this huge data (because the purpose of storing and processing of the data is to serve the 
business decisions better based on the insights drawn out of it )

now traditional monolithic systems or monolithic tech stock cannot handle big data we need new tech stock which is distributed system
a distributed system is the cluster of machines or nodes which are connected over a network and they have their own resources for distributed processing 
basically a monolithic system is one powerful machine which has resources 
compute: 4 CPU cores
memory: 8 GB ram
storage: 1 TB hardisk

the problem with monolithic system is we cannot scale the system like if storage increases we cannot add up compute or memory efficiently 
and eventually performance will not be doubled by increasing the resources as single system has hardware limitations 

lets say we need to store 2TB of data then we may use external hardisk we may increase resources (vertical scaling) may be memory but not compute 
but what about processing and performance ???

this is where distributed system which has distributed storage and distributed processing and this combination which brings horizontal 
scalability perfectly suits big data systems

# Hadoop Overview
Hadoop is the distributed framework or eco system for solving big data problems
Hadoop has 3 major components 
HDFS: Hadoop distributed file system (distirbuted storage)
Map Reduce: its a distributed processing framework in hadoop and is java native
YARN: Yet another resource negotiator used for negotiating or managing resources 
 around these 3 core components there are other tools or servivces like 
 sqoop : which is the tool used for ingestion from external sources to HDFS using sqoop import and vice versa using sqoop export
 pig : pig is a scripting language used to clean the data 
 hive : hive is a SQL kind of interface to query data 
 all these tools would use map reduce jobs under neath the herd 
 OOZIE : its XML based workflow schedulder in hadoop
 Hbase : its NoSQL database service in Hadoop eco system 
 ex: lets say we had 10 lakh records in a emp table and we want to filter id 800000 then when you run query using hive 
 select * from emp where id = 800000 it goes based on sequential search and it takes lot of time 
 but hbase query goes in random search and retrieval is faster ....so in banks or retail industry if they wanted to retrieve particular customer info 
 then they can use NoSQL databases

 now people are moving away from hadoop eco system tools which is a on-premise distributed framework to solve big data problems into cloud based 
 like azure Cosmos DB instead of hbase 
 Azure data factory instead of Oozie 
 azure data factory is used instead of sqoop for data movement and also data integration using GUI based pipelines 
 Hive is still used by many companies still 
 instead of map reduce spark is used because map reduce is java native and is very slow  

 # Cloud and its advantages
 in the On-premise i.e at our location if you want to run a 50 node hadoop cluster we need to buy the servers procure space for it install software recruit admins 
 and also we need to pay upfront cost for it whether you use it or not so this takes months 
 its like if you want to set-up a start-up company then if you construct your own office and set up all the infrastructure yourselves its quite expensive and time  bound  but what if there are some realters who build commercial spaces for rent and you just plug and play per seat then you get out write advantage that you can 
 start your start-up immediately this is cloud 
 and advantages of cloud 
 scalability : for example if amazon wanted to run some sales then they need to handle extra traffic from lot of customers now using cloud they can spin up their 
 resources just by using the click 
 capex Vs opex cost : when in on-premise  along with operational cost you need to take care of  capital expenditure (upfront cost) but with cloud you need to just  worry about operational expenditure
 Agility: using cloud within 10 minutes you can spin up 10 machines or as many machines but with on-premises it takes months
 Geo distribution : lets say the server which is hosting your website is in India and 30% of your customers are from US then they face latency in accessing the 
 website. in-order to address the issue if your website is hosted in two different servers each one placed in India and US then there will be no network issue 
 or latency issue
 Disaster Recovery: if your website is being hosted in multiple servers in different locations then even if one location is prone to disaster then other server would automatically receives the cusotmers request but with some latency without interupting your business 
 cost effective: as you would pay only for what you use its cost effective compare to on-premise 

 what are the different types of clouds :
 public cloud : they not only use their resources but also would rent and most of the people would rent them because of their brand value like 
 Amazon AWS Microsoft Azure Google GCP 
 private cloud : this is costly but used by those financial forms like JP morgan or cisco use their own inhouse cloud and its meant only for them
 hybrid cloud : its like combination of public plus private where they gona secure their senstive data within private cloud and gona use public cloud for general   purpose

 public clouds examples: Amazon AWS Microsoft Azure   Google GCP 

 # Spark at highlevel
 Hadoop has 3 core components HDFS, Map Reduce and YARN 
 but Map reduce has dead now it has been replaced by spark this is because of Map reduce hardness of coding and it slowness
 spark is 10X - 100X times faster compared to Map reduce

 spark is general purpose in-memory compute engine which needs 2 components storage and resource manager to plug and play 
 Storage : HDFS/ AWS S3/ AZURE ADLS GEN2 / GCS / Local Storage
 Resource Manager: YARN/ MESOS/ Kubernetes
 and spark can be written in Java, Scala and Python 
we learn pyspark here in here as python is flexible for writing spark application
 
# Database Vs Datawarehouse Vs DataLake
A database holds transactional data which is the latest data like day to day data ..it is a Online Transactional Processing System (OLTP)
A database enforces schema on write whinch means schema is defined even before data is loaded into the table or database 
if schema mismatches then insert statement errors out even before data is loaded this is schema on write. database stores only structured data
Ex: oracle, mysql 
A datawarehouse is used for analytical processing of historical data and derive insights 
we need to run complex queries in-order to analyse data thats why we cannot run analytical queries on the database as its slows down the day to day 
writes...datawarehouse follows ETL Process extract data from multiple sources and transform it before we load it into datawarehouse 
transform is a comolex process before we load the data 
datawarehouses also enforces scheme on write. datawarehouse stores only structured data
Ex: Teradata
a datalake is something which is used to draw insights from huge amount of data ...in datalake the data is raw we enforce sxhema when we read the data 
so datalake enforces schema on read just like hive tables where data is prresent in some location and schema is in other location we enforces schema 
while we read the data datalake follows ELT process like first all rawdata is loaded into datalake like HDFS , AWS S3 etc and then we read the data by 
enforcing a schema. datalake can store structured or unstructured data 

# Data Engineering workflow 
Source --> Ingestion --> storage or datalake ---> processing ---> serving layer
from different multiple sources say RDBMS or Web applications or Mobile apps or files etc the data is first ingested into data lake or storage layer and then 
the data from data lake is processed nothing but data quality checks , aggregations , transformations , business logics is applied and is moved to serving layer 
where database / datawarehouse would be serving layer if it is for reporting ...if it is for building custom UI then we use NoSQL Database

if it is on-premise .i.e Hadoop then 
MySQL ---> Sqoop ---> HDFS ----> Map Reduce/Spark ---> Hive/Hbase

if it is Azure Cloud then 
Multiple Sources ----> Azure data Factory (ADF) -----> ADLS Gen 2 -----> Azure Databricks / Azure Synapse ----> Azure SQL / cosmos DB 
if it is AWS Cloud then 
Multiple Sources ----> AWS glue ----> AWS S3 ----> AWS Databricks/ Athena / Redshift -----> AWS RDS/ Dynamo DB 

basically computation is of 2 types serverless computation Vs serverful or managed computation 
athena is an serverless SQL quering service which uses resources from shared pool no dedicated clusters or resources 
where as redshift is managed datawarehouse service which uses dedicated redshift cluster or servers and queries are run inside it 
we use athena when we need to run adhoc queires on high level and we use redshift where we need to run analytical queries 
athena charges based on the data scanned by the query for 1 TB $5 is charged for 100 gb it is $0.5 but for redshift it is charged 
based on nodes per hour 
when it comes to azure we have azure synapse serverless Vs azure synapse dedicated pool 

In azure we have 
azure data factory for ingestion 
ADLS Gen2 for data lake
azure databricks for processing 
azure synapse for processing 
cosmos db for serving 
azure SQL for serving 
azure data factory for orchestration and scheduling of workflows 


