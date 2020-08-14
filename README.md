# Big-Data-and-Hadoop

# Introduction to Big Data

Big Data is a term applied to data sets whose size is beyond the ability of commonly used software tools to capture, manage, and process within a tolerable elapsed time. Big Data sizes are a constantly moving target currently ranging from a few dozen terabytes to many petabytes in a single data set. It is the realization of greater business intelligence by storing, processing, and analyzing data that was previously ignored due to the limitations of traditional data management technologies.

The challenges include capture, storage, search, sharing, analysis, and visualization. The trend to larger data sets is due to the additional information derivable from analysis of a single large set of related data, as compared to separate smaller sets with the same total amount of data, allowing correlations to be found to "spot business trends, determine quality of research, prevent diseases, link legal citations, combat crime, and determine real-time roadway traffic conditions.



# Big data Key Features & Attributes
Big Data involves processing of huge volume of unstructured data , structured & semi-structured and across different nodes using languages such as "MR", "Hive" and "Pig".

Big Data supports Volume: Large volumes of data, Velocity: Quickly moving data,

Variety: structured, unstructured, images. Veracity: Trust and integrity is a challenge and a must and is important for big data just as for traditional relational DBs.



# Introduction to Hadoop
Hadoop is an Apache open source project that provides a parallel storage and processing framework. Its primary purpose is to run MR batch programs in parallel on tens to thousands of server nodes.

One of Hadoop’s greatest benefits is the ability of programmers to write application modules in almost any language and run them in parallel on the same cluster that stores the data. This is a profound change! With Hadoop, any programmer can harness the power and capacity of thousands of CPUs and hard drives simultaneously.

More advantages of Hadoop include affordability (it runs on commodity hardware), open source (free download from Cloudera), and agility (store any data, run any analysis) and  focus is on supporting redundancy, distributed architectures, and parallel processing.

Hadoop framework allows the distributed processing of large data set across clusters of computers.

Hadoop is a distributed file system and data processing engine has two components:

The Hadoop distributed file system (HDFS), which supports data in structured relational form, in unstructured form, and in any form in between and is designed to handle extremely high volumes of data in any structure.
The MapReduce program manages applications on multiple distributed servers.
Hadoop distributed file system
HDFS – Hadoop distributed file system scales out to large clusters of servers and storage to manage huge data sets and spread them across the servers. HDFS  is designed for scalability and fault tolerance. HDFS stores large files by dividing them into blocks (usually64 or 128 MB) and replicating the blocks on three or more servers.

HDFS provides APIs for MR applications to read and writedata in parallel. Capacity and performance can be scaled by adding Data Nodes, and a single Name Node mechanism manages data placement and monitors server availability. HDFS clusters in production use today reliably hold petabytes of data on thousands of nodes.

HDFS is distributed across nodes and Natively Redundant. Namenode tracks locations in distribution.



# Map Reduce(MR)
MapReduce helps programmers solve data-parallel problems for which the dataset can be sub-divided into small parts and processed independently.

MR refers to the application modules written by a programmer that run in two phases: first mapping the data (extract) then reducing it (transform).

MR is an important advance because it allows ordinary developers, not just those skilled in high-performance computing, to use parallel programming constructs without worrying about the complex details of intra-cluster communication, task monitoring, and failure handling. MR simplifies all that.

The system splits the input data-set into multiple chunks, each of which is assigned a map task that can process the data in parallel.

Each map task reads the input as a set of (key, value) pairs and produces a transformed set of (key, value) pairs as the output. The framework shuffles and sorts outputs of the map tasks, sending the intermediate (key, value) pairs to the reduce tasks, which group them into final results. MapReduce uses JobTracker and TaskTracker mechanisms to schedule tasks, monitor them, and restart any that fail.

# Name Node and Data Nodes
HDFS consists of a single Name Node, a master server that manages the file system namespace and regulates access to files by clients. In addition, there are a number of Data Nodes, usually one per node in the cluster, which manage storage attached to the nodes that they run on. HDFS exposes a file system namespace and allows user data to be stored in files. Internally, a file is split into one or more blocks and these blocks are stored in a set of Data Nodes.

The Name Node executes file system namespace operations like opening, closing, and renaming files and directories. It also determines the mapping of blocks to Data Nodes.

The Data Nodes are responsible for serving read and write requests from the file system’s clients. And also perform block creation, deletion, and replication upon instruction from the Name Node. 

Master (Job tracker) is the point of interaction between users and the map/reduce framework. When a map/reduce job is submitted, Job tracker puts it in a queue of pending jobs and executes them on a first-come/first-served basis and then manages the assignment of map and reduce tasks to the task trackers.Slaves (task tracker) execute tasks upon instruction from the Master (Job tracker) and also handle data motion between the map and reduce phases.



# Hadoop Architecture
MR programming implemented by Apache Hadoop, breaks-up a batch job into many smaller tasks for parallel processing on a distributed system. HDFS, the distributed file system stores the data reliably.



# Hadoop Cluster
In addition to MR and HDFS, Apache Hadoop includes many other components which are useful for ETL and Data warehouse support.

#Apache Flume
Apache Flume is a distributed system for collecting, aggregating, and moving large amounts of data from multiple sources into HDFS or another central data store. Enterprises typically collect log files on application servers or other systems and archive the log files in order to comply with regulations. Being able to ingest and analyze that unstructured or semi-structured data in Hadoop can turn this passive resource into a valuable asset.

Flume can be used to transport massive quantities of event data including but not limited to network traffic data, social-media-generated data, email messages and pretty much any data source possible.



# Apache Sqoop
Apache Sqoop is a tool for transferring data between Hadoop and relational databases. Sqoop  supports importing data from MySQL or Oracle database into HDFS, run Map Reduce on the data, and then export the data back into an RDBMS. Sqoop automates these processes, using MR to import and export the data in parallel with fault-tolerance.

 

# Apache Hive
Apache Hive is a data warehouse infrastructure built on top of Hadoop for providing data summarization, query, and analysis.

It supports analysis of large datasets stored in Hadoop's HDFS and compatible file systems. It provides an SQL-like language called HiveQL with schema on read and transparently converts queries to map/reduce. To accelerate queries, it provides indexes, including bitmap indexes

By default, Hive stores metadata in an embedded Apache Derby database, and other client/server databases like Mysql. File formats supported in Hive are TEXTFILE, SEQUENCEFILE, ORC and Record Columnar File.



# Apache Pig
Apache Pig is a platform for analyzing large data sets that consists of a high-level language for expressing data analysis programs, coupled with infrastructure for evaluating these programs. The prominent property of Pig programs is their structure is responsive to extensive parallelization, which in turns enables them to handle very large data sets.

Apache Pig has Pig Latin language a high-level platform for creating MR programs used with Hadoop. Pig Latin abstracts the programming from the MR idiom into a notation which makes MR programming high level, similar to that of SQL for RDBMS systems. Pig Latin can be extended using UDF (User Defined Functions) which the user can write in Java, Python, JavaScript, Ruby or Groovy and then call directly from the language.



# NO-SQL Databases
No-SQl (Not Only SQL): Databases that “move beyond” relational data models (i.e., no tables, limited or no use of SQL) are non-relational, distributed, open-source, horizontally, callable largely distributed database system that enables rapid, ad-hoc organization and analysis of extremely high-volume, disparate data types. NoSQL databases are sometimes referred as Big Data databases and a myriad of other terms and were developed in response to the sheer volume of data being generated, stored and analyzed by modern users (user-generated data) and their applications (machine-generated data).

There are four general types of NoSQL databases:-

Key-Value store – These are some of the least complex NoSQL options. These databases are designed for storing data in a schema-less way. In a key-value store, all of the data consists of an indexed key and a value. Examples - Cassandra, DyanmoDB, Azure Table Storage (ATS), Riak, BerkeleyDB.

Column store(wide-column stores) – These databases are designed for storing data tables as sections of columns of data, rather than as rows of data. Wide-column stores offer very high performance and a highly scalable architecture. Examples include: HBase, Big Table and Hyper Table.

Document database – Key-value stores where “documents” contain more complex in that they contain data and each document is assigned a unique key, which is used to retrieve the document. These are designed for storing, retrieving, and managing document-oriented information, also known as semi-structured data. Examples include: MongoDB and CouchDB.

Graph database – Based on graph theory, these databases are designed for data whose relations are well represented as a graph and has elements which are interconnected, with an undetermined number of relations between them. Examples include: Neo4J and Polyglot.
