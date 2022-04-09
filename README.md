# BigDataSpark

## Objective
The objective of this notebook is to:
><li>Give a proper understanding about the different PySpark functions available. </li>
><li>A short introduction to Google Colab, as that is the platform on which this notebook is written on. </li>

Once you complete this notebook, you should be able to write pyspark programs in an efficent way. The ideal way to use this is by going through the examples given and then trying them on Colab. At the end there are a few hands on questions which you can use to evaluate yourself.

If you are working in the field of big data, you must have definelty heard of spark. If you look at the [Apache Spark](https://spark.apache.org/) website, you will see that it is said to be a `Lightning-fast unified analytics engine`. PySpark is a flavour of Spark used for processing and analysing massive volumes of data. If you are familiar with python and have tried it for huge datasets, you should know that the execution time can get ridiculous. Enter PySpark!

Imagine your data resides in a distributed manner at different places. If you try brining your data to one point and executing your code there, not only would that be inefficent, but also cause memory issues. Now let's say your code goes to the data rather than the data coming to where your code. This will help avoid unneccesary data movement which will thereby decrease the running time. 

PySpark is the Python API of Spark; which means it can do almost all the things python can. Machine learning(ML) pipelines, exploratory data analysis (at scale), ETLs for data platform, and much more! And all of them in a distributed manner. One of the best parts of pyspark is that if you are already familiar with python, it's really easy to learn.

Apart from PySpark, there is another language called Scala used for big data processing. Scala is frequently over 10 times faster than *Python*, as it is native for Hadoop as its based on JVM. But PySpark is getting adopted at a fast rate because of the ease of use, easier learning curve and ML capabilities.

I will briefly explain how a PySpark job works, but I strongly recommend you read more about the [architecture](https://data-flair.training/blogs/how-apache-spark-works/) and how everything works. Now, before I get into it, let me talk about some <u>basic jargons</u> first:

<b>Cluster</b> is a set of loosely or tightly connected computers that work together so that they can be viewed as a single system.

<b>Hadoop</b> is an open source, scalable, and fault tolerant framework written in Java. It efficiently processes large volumes of data on a cluster of commodity hardware. Hadoop is not only a storage system but is a platform for large data storage as well as processing.

<b>HDFS</b> (Hadoop distributed file system). It is one of the world's most reliable storage system. HDFS is a Filesystem of Hadoop designed for storing very large files running on a cluster of commodity hardware.

<b>MapReduce</b> is a data Processing framework, which has 2 phases - Mapper and Reducer. The map procedure performs filtering and sorting, and the reduce method performs a summary operation. It usually runs on a hadoop cluster.

<b>Transformation</b> refers to the operations applied on a dataset to create a new dataset. Filter, groupBy and map are the examples of transformations.

<b>Actions</b> Actions refer to an operation which instructs Spark to perform computation and send the result back to driver. This is an example of action.

Alright! Now that that's out of the way, let me explain how a spark job runs. In simple terma, each time you submit a pyspark job, the code gets internally converted into a MapReduce program and gets executed in the Java virtual machine. Now one of the thoughts that might be popping in your mind will probably be: <br>`So the code gets converted into a MapReduce program. Wouldn't that mean MapReduce is faster than pySpark?`<br> Well, the answer is a big NO. This is what makes spark jobs special. Spark is capable of handling a massive amount of data at a time, in it's distributed environment. It does this through <u>in-memory processing</u>, which is what makes it almost 100 times faster than Hadoop. Another factor which amkes it fast is <u>Lazy Evaluation</u>. Spark delays its evaluation as much as it can. Each time you  submit a job, spark creates an action plan for how to execute the code, and then does nothing. Finally, when you ask for the result(i.e, calls an action), it executes the plan, which is basically all the transofrmations you have mentioned in your code. That's basically the gist of it. 

Now lastly, I want to talk about on more thing. Spark mainly consists of 4 modules:

<ol>
    <li>Spark SQL - helps to write  spark programs using SQL like queries.</li>
    <li>Spark Streaming - is an extension of the core Spark API that enables scalable, high-throughput, fault-tolerant stream processing of live data streams. used heavily in processing of social media data.</li>
    <li>Spark MLLib - is the machine learning component of SPark. It helps train ML models on massive datasets with very high efficeny. </li>
    <li>Spark GraphX - is the visualization component of Spark. It enables users to view data both as graphs and as collections without data movement or duplication.</li>
</ol>

Hopefully this image gives a better idea of what I am talking about:
<img alt="Spark Modules" src="https://2s7gjr373w3x22jf92z99mgm5w-wpengine.netdna-ssl.com/wp-content/uploads/2015/11/spark-streaming-datanami.png" />
<center><font color='#666956'>Source: Datanami</font><center>

