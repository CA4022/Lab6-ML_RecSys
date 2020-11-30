# Machine Learning with SPARK MLlib
This Lab provides some pointers and resources for Machine Learning with Spark MLib.
The official guide is available [here](https://spark.apache.org/docs/2.3.0/ml-guide.html)

We will start by running some of the examples available in `<YOUR_SPARK_HOME>/examples/src/main/python/ml/`
The corresponding code is also illustrated in the [MLlib manual](https://spark.apache.org/docs/2.3.0/ml-guide.html)

## Statistical Correlation
The example is illustrated [here](https://spark.apache.org/docs/2.3.0/ml-guide.html) and contained in `correlation_example.py`
* start spark master and slave as seen in previous labs
* submit the task to your spark server
  - `$ bin/spark-submit --master local[4] examples/src/main/python/ml/correlation_example.py`
* check in your output the spearman's and pearson's correlation matrix for the input vectors

## K-Means clustering
The example is illustrated [here](https://spark.apache.org/docs/2.3.0/ml-clustering.html#k-means) and contained in `kmeans_example.py`
* start spark master and slave as seen in previous labs (if not running already)
* submit the task to your spark server
  - `$ bin/spark-submit --master local[4] examples/src/main/python/ml/kmeans_example.py`
* check output

## Features Extraction, Transformation and Selection
[This section](https://spark.apache.org/docs/2.3.0/ml-features.html) of the MLlib main guide provides several mechanisms to extract features from raw data (e.g. TF-IDF for vectorizatiation of text features), transform features (e.g. n-grams used for shingling, remove stop words, tokenize, ...), select a subset of relevant features (e.g. from a vector column), and hashing (including LSH, min-hash seen in item similarity and used for clustering and recommendation).

Note the following:
  * some of the functionalities work on RDDs only, some on DataFrames only
  * you are probably likely to have a mix of data types in complex projects (you can see that looking at what data structure is used to wrap the data) 
  * when processing documents, it is very common to use these methods to transform text into numeric vectors/matrixes, which is what the ML algorithms use

## ML Pipelines
  * High-level APIs working on DataFrames
  * Example: Spam email detection (modified from [pipeline_example.py](https://spark.apache.org/docs/2.3.0/ml-pipeline.html#example-pipeline))
    - python code in spam-ham.py
    - note that we omit reading the data from the file (which is not very relevant here). Instead, we provide the data directly using strings in the program
    - look into the different steps: prepare training documents, configure pipeline, fit the model with training documents (estimator), prepare test documents, make prediction on test documents (transformer)
    - start spark master and slave and use spark-submit to run spam-ham.py
  * Question: how would you modify the code to do sentiment analysis, using logistic regression?
  * 

## Python 
* [Pyspark mllib modules](https://spark.apache.org/docs/2.3.0/api/python/pyspark.mllib.html)
* [Pyspark ml modules](https://spark.apache.org/docs/2.3.0/api/python/pyspark.ml.html)

## Java
* Machine Learning with [MLib in Java](https://www.tutorialkart.com/apache-spark/apache-spark-mllib-scalable-machine-learning-library/)

# Recommender Systems example and resources
TBD
<!--* [Example Collaborative Filtering](https://www.tutorialspoint.com/pyspark/pyspark_mllib.htm)
Recommendation with Mlib in Python:
Python/Scala: http://ampcamp.berkeley.edu/5/exercises/movie-recommendation-with-mllib.html
https://medium.com/analytics-vidhya/crafting-recommendation-engine-in-pyspark-a7ca242ad40a
PySpark and MLIB tutorial: https://www.tutorialspoint.com/pyspark/pyspark_mllib.htm
Databrics: https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/3741049972324885/1723574684687027/4413065072037724/latest.html
CollabFiltering with ALS https://towardsdatascience.com/build-recommendation-system-with-pyspark-using-alternating-least-squares-als-matrix-factorisation-ebe1ad2e7679
BookRecommendation: https://towardsdatascience.com/building-a-recommendation-engine-to-recommend-books-in-spark-f09334d47d67 -->

