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
 
