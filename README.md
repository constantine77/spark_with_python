# spark_with_python
<h1 align="center">
SPARK with Python
</h1>
The goal of this project is to learn all the technical details of how Spark works. Next, explore the RDD API, the original core abstraction of Spark. Finally, discover how to become more proficient using Spark SQL and DataFrames.
#### Table of Contents

1. [Theory](#Theory)
2. [Example2](#example2)
3. [PythonFundamentals:](#pythonfundamentals)
  * 3.1 [Modularity:](#modularity)
  
## Theory

Apache Spark is an open-source cluster computing framework for real-time processing. It is of the most successful projects in the Apache Software Foundation. Spark has clearly evolved as the market leader for Big Data processing. Today, Spark is being adopted by major players like Amazon, eBay, and Yahoo! Many organizations run Spark on clusters with thousands of nodes.

As we can see, there is a colossal amount of data that the internet world necessitates to process in seconds. We will go through all the stages of handling big data in enterprises and discover the need for a Real Time Processing Framework called Apache Spark.

Let us look at some of these use cases of Real Time Analytics:
	1. Healthcare: Healthcare domain uses Real Time analysis to continuously check the medical status of critical patients. Hospitals on the look out for blood and organ transplants need to stay in a real-time contact with each other during emergencies. Getting medical attention on time is a matter of life and death for patients.
	2. Government: Government agencies perform Real Time Analysis mostly in the field of national security. Countries need to continuously keep a track of all the military and police agencies for updates regarding threats to security.
	3. Telecommunications: Companies revolving around services in the form of calls, video chats and streaming use real-time analysis to reduce customer churn and stay ahead of the competition. They also extract measurements of jitter and delay in mobile networks to improve customer experiences.
	4. Banking: Banking transacts with almost all of the world’s money. It becomes very important to ensure fault tolerant transactions across the whole system. Fraud detection is made possible through real-time analytics in banking.
	5. Stock Market: Stockbrokers use real-time analytics to predict the movement of stock portfolios. Companies re-think their business model after using real-time analytics to analyze the market demand for their brand.

The first of the many questions everyone asks when it comes to Spark is, “Why Spark when we have Hadoop already?“. 
Here, we can draw out one of the key differentiators between Hadoop and Spark. Hadoop is based on batch processing of big data. This means that the data is stored over a period of time and is then processed using Hadoop. Whereas in Spark, processing can take place in real-time. This real-time processing power in Spark helps us to solve the use cases of Real Time Analytics we saw in the previous section. Alongside this, Spark is also able to do batch processing 100 times faster than that of Hadoop MapReduce (Processing framework in Apache Hadoop). Therefore, Apache Spark is the go-to tool for big data processing in the industry.

Spark has the following features:

Polyglot:
Spark provides high-level APIs in Java, Scala, Python and R. Spark code can be written in any of these four languages. It provides a shell in Scala and Python. The Scala shell can be accessed through ./bin/spark-shell and Python shell through./bin/pyspark from the installed directory.
Speed:
Spark runs up to 100 times faster than Hadoop MapReduce for large-scale data processing. Spark is able to achieve this speed through controlled partitioning. It manages data using partitions that help parallelize distributed data processing with minimal network traffic.
Multiple Formats:
Spark supports multiple data sources such as Parquet, JSON, Hive and Cassandra apart from the usual formats such as text files, CSV and RDBMS tables. The Data Source API provides a pluggable mechanism for accessing structured data though Spark SQL. Data sources can be more than just simple pipes that convert data and pull it into Spark
Real Time Computation:
Spark’s computation is real-time and has low latency because of its in-memory computation. Spark is designed for massive scalability and the Spark team has documented users of the system running production clusters with thousands of nodes and supports several computational models.
Hadoop Integration:
Apache Spark provides smooth compatibility with Hadoop. This is a boon for all the Big Data engineers who started their careers with Hadoop. Spark is a potential replacement for the MapReduce functions of Hadoop, while Spark has the ability to run on top of an existing Hadoop cluster using YARN for resource scheduling
Lazy Evaluation:
Apache Spark delays its evaluation till it is absolutely necessary. This is one of the key factors contributing to its speed. For transformations, Spark adds them to a DAG (Directed Acyclic Graph) of computation and only when the driver requests some data, does this DAG actually gets executed.
Lazy Evaluation -  just tell where the data location (just tell the friend I have a box of candies but I'm not providing any details action to perform, the same as when you map an RDD. To finish any action I have to tell my friend which action to perform. RDD.count() etc.
Parallel Processing: Spark is fast and parallel processing is why it's fast.
Spark Shell: 
Spark’s shell provides a simple way to learn the API, as well as a powerful tool to analyze data interactively.
Spark Session: 
In earlier versions of Spark, Spark Context was the entry point for Spark. For every other API, we needed to use different contexts. For streaming, we needed StreamingContext, for SQL sqlContext and for hive HiveContext. To solve this issue, SparkSession came into the picture. It is essentially a combination of SQLContext, HiveContext and future StreamingContext.
Summary: the spark session is one of the variety of entry points to the cluster.

Spark Aplication Deployment(pic):

![alt text](https://github.com/constantine77/spark_with_python/blob/master/src/screenshots/data-with-spark.jpg)

PySpark SparkContext and Data Flow:

Talking about Spark with Python, working with RDDs is made possible by the library Py4j. PySpark Shell links the Python API to Spark Core and initializes the Spark Context. Spark Context is at the heart of any Spark application.
1. Spark Context sets up internal services and establishes a connection to a Spark execution environment.
2. The Spark Context object in driver program coordinates all the distributed processes and allows for resource allocation.
3. Cluster Managers provide Executors, which are JVM processes with logic.
4. Spark Context objects send the application to executors.
5. Spark Context executes tasks in each executor.
![alt text](https://github.com/constantine77/spark_with_python/blob/master/src/screenshots/pyspark.png)


 
Software Prerequisites
•    Apache Spark (Downloadable from http://spark.apache.org/downloads.html)
•    Python Installed
Apache Spark comes with an interactive shell for python as it does for Scala. The shell for python is known as “PySpark”. To use PySpark you will have to have python installed on your machine.

1. Choose a Spark release and Download Spark https://www.apache.org/dyn/closer.lua/spark/spark-2.3.1/spark-2.3.1-bin-hadoop2.7.tgz
2. Make sure you have java installed on your machine.
3. Go to your home directory (command in bold below)
cd ~
4. Unzip the folder in your home directory using the following command.
tar -zxvf spark-1.6.0-bin-hadoop2.6.tgz
5. Use the following command to see that you have a .bash_profile
ls -a
6. Next, we will edit our .bash_profile so we can open a spark notebook in any directory.
7. Don’t remove anything in your .bash_profile. Only add the following
export SPARK_PATH=~/spark-1.6.0-bin-hadoop2.6 
export PYSPARK_DRIVER_PYTHON="jupyter" 
export PYSPARK_DRIVER_PYTHON_OPTS="notebook" 
8. Type the following into your terminal
source .bash_profile
9.Go to spark folder and Run bin/PySpark
Core Spark Concepts:
        1. Drivers and Executors
        2. Spark Context and Configurations
        3. Transformation and Actions
        4. Building an end to end application
        5. Introduce Directed Acyclic Graph (DAG)

        PySpark is the Python API to Spark.
        
        Drivers and Executors:
        
        At a high level, every Spark application consists of a driver program that launches various parallel operations on a cluster. Typical driver program could be the Spark shell itself, and you could just type in the operations you wanted to run.
        Driver program access Spark through a SparkContext object, which represents a connection to a computing cluster. In the shell, a SparkContext is automatically created for you as the variable called ‘sc’.
        Once you have a SparkContext, you can use it to build RDDs
        sc.textFile("README.md")
        This RDD represents the lines of a text in a file and subsequently we can run more operations on these lines like -
        lines.count() # Count the number of items in this RDD
        
        To run these operations, driver programs typically manage a number of nodes called executors. For example, if we were running the count() operation on a cluster, different machines might count lines in different ranges of the file. The below schematic diagram shows how Spark executes on a cluster.
        
        
        
For example, we could extend our README example by filtering the lines in the file that contain a word, such as Python:
### Python filtering example
lines = sc.textFile("README.md") # Create an RDD called lines
pythonLines = lines.filter(lambda line: "Python" in line)
pythonLines.first()






