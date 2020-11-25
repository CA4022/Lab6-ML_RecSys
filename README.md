# Machine Learning with SPARK MLlib
This Lab provides some pointers and resources for Machine Learning with Spark MLib.
The official guide is available [here](https://spark.apache.org/docs/2.3.0/ml-guide.html)

We will start by running some of the examples available in <YOUR_SPARK_HOME>/examples/src/main/python/ml/
The corresponding code is also illustrated in the [MLlib manual](https://spark.apache.org/docs/2.3.0/ml-guide.html)

## Statistical Correlation
The example is illustrated [here](https://spark.apache.org/docs/2.3.0/ml-guide.html) and contained in correlation_example.py
* start spark master and slave as seen in previous labs
* submit the task to your spark server
  - bin/spark-submit --master local[4] examples/src/main/python/ml/correlation_example.py
* check in your output the spearman's and pearson's correlation matrix for the input vectors

## Python 
* [Pyspark mllib modules](https://spark.apache.org/docs/2.3.0/api/python/pyspark.mllib.html)
* [Pyspark ml modules](https://spark.apache.org/docs/2.3.0/api/python/pyspark.ml.html)

## Java
* Machine Learning with [MLib in Java] (https://www.tutorialkart.com/apache-spark/apache-spark-mllib-scalable-machine-learning-library/)

# Recommender Systems examples and pointers
<!--* [Example Collaborative Filtering](https://www.tutorialspoint.com/pyspark/pyspark_mllib.htm)>

