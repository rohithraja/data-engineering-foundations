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
