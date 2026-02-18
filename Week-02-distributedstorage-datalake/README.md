# HDFS Overview
lets say we had a 4 node cluster and we are storing a 500 mb file in HDFS then each node will get one block (considering 128MB block size) and Name Node which is the master stores meta data about actual data present in data nodes this hadoop cluster works as per master slave architecture where name node is master node which holds data and data nodes are slave nodes which holds actual data interms of blocks...

File1 B1 DN1
File1 B2 DN2
File1 B3 DN3
File1 B4 DN4

In real projects for example flipkart has 1000 node cluster then if they wanted to store 1 gb file with blocksize of 
128mb we have 8 blocks and we need atleast 8 nodes for parallelism
64mb we have 16 blocks and we need atleast 16 nodes for parallelism

but if we say block size is 1mb and file size is 10gb then we need 10240 blocks to be stored in 1000 nodes here we may achieve parallelism but it over burdens 
name node which stores meta data ..for data node failure we have default replication factor of 3 where each block is replicated by default in 3 nodes 

whenever there is namenode burden issue as per latest hadoop version there is a concept of we can have multiple namenodes where metadata is shared between them 
this concept is known as namenode federation and for name node failure we have secondary name node 

lets say there are 30 name nodes then 10 nodes are kept in bangalore in 1 rack 
10 nodes are kept in sanfrancisco in 1 rack
10 nodes are kept in australia in 1 rack 

now each block is replicated thrice in 3 different nodes and all these 3 different nodes will be stored in atleast 2 different regions i.e in 2 different racks 
these 3 different nodes will not be present in the same rack 
