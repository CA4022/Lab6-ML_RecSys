# Machine Learning with SPARK
This Lab provides some pointers and resources for Machine Learning with Spark.
You can see the main ML library documentation [here](https://spark.apache.org/docs/latest/ml-guide.html)

* spark.ml package is now the primary API (data frame based api)
* spark.mllib package is now in maintenance mode (RDD-based API) available [here](https://spark.apache.org/docs/latest/mllib-guide.html)

<!--Note that we will look into MLlib for the examples below and this is recommended also for backward compatibility with RDDs, but -->
Note that SparkML (on DataFrames) supports ML pipelines and should therefore be your library of choice for ML on Spark (e.g. in your assignment).

<!--Further links for Java:
* Machine Learning with [MLib in Java](https://www.tutorialkart.com/apache-spark/apache-spark-mllib-scalable-machine-learning-library/)-->

Further links for Python: 
<!--* [Pyspark mllib modules](https://spark.apache.org/docs/2.3.0/api/python/pyspark.mllib.html)-->
* [Pyspark ml modules](https://spark.apache.org/docs/latest/api/python/reference/pyspark.ml.html)
* [Connect Jupiter Notebook to a Spark Cluster](https://www.bmc.com/blogs/jupyter-notebooks-apache-spark/)


We will start by running some of the examples available in `<YOUR_SPARK_HOME>/examples/src/main/python/ml/`
The corresponding code is also illustrated in the [MLlib manual](https://spark.apache.org/docs/latest/ml-guide.html)

## Statistical Correlation
The example is illustrated [here](https://spark.apache.org/docs/latest/ml-statistics.html#correlation) and contained in `correlation_example.py`
* start spark master and slave as seen in previous labs
* submit the task to your spark server
  - `$ bin/spark-submit --master local[4] examples/src/main/python/ml/correlation_example.py`
* check in your output the spearman's and pearson's correlation matrix for the input vectors

## K-Means clustering
The example is illustrated [here](https://spark.apache.org/docs/latest/ml-clustering.html#k-means) and contained in `kmeans_example.py`
* start spark master and slave as seen in previous labs (if not running already)
* submit the task to your spark server
  - `$ bin/spark-submit --master local[4] examples/src/main/python/ml/kmeans_example.py`
* check output

## Features Extraction, Transformation and Selection
[This section](https://spark.apache.org/docs/latest/ml-features.html) of the MLlib main guide provides several mechanisms to extract features from raw data (e.g. TF-IDF for vectorizatiation of text features), transform features (e.g. n-grams used for shingling, remove stop words, tokenize, ...), select a subset of relevant features (e.g. from a vector column), and hashing (including LSH, min-hash seen in item similarity and used for clustering and recommendation).

Note the following:
  <!--* some of the functionalities work on RDDs only, some on DataFrames only-->
  * you are probably likely to have a mix of data types (RDD and DataFrames) in complex projects (you can see that looking at what data structure is used to wrap the data) 
  * when processing documents, it is very common to use these methods to transform text into numeric vectors/matrixes, which is what the ML algorithms use

Try and run the following examples from the [spark documentation](https://spark.apache.org/docs/latest/ml-features.html):
  * Word2Vec or CountVectoriser
  * StopWordsRemover (try it with a different language)
  * n-grams 

Note the order of some of these in the list, as some take as input the output of a previous transformation (e.g. tokeniser/stopwordsremover/n-grams)  

## ML Pipelines
  * High-level APIs working on DataFrames
  * Example: Spam email detection (modified from [pipeline_example.py](https://spark.apache.org/docs/latest/ml-pipeline.html#example-pipeline))
    - python code in spam-ham.py
    - note that we omit reading the data from the file (which is not very relevant here). Instead, we provide the data directly using strings in the program
    - look into the different steps: prepare training documents, configure pipeline, fit the model with training documents (estimator), prepare test documents, make prediction on test documents (transformer)
    - start spark master and slave and use spark-submit to run spam-ham.py
  * Question: how would you modify the code to do sentiment analysis, using logistic regression?
  
##  Classification/Clustering examples
 * Experiment with some of the different examples of [Classification](https://spark.apache.org/docs/latest/ml-classification-regression.html) and [Clustering](https://spark.apache.org/docs/latest/ml-clustering.html) in the Spark Documentation.

# Recommender Systems example and resources
Spark recommendation is based on Alternating Least Squares (ALS) matrix factorisation algorithms. Some example of how to build a RecSys based on Collaborative filtering with ALS in PySpark include:
  * [Movie recommendation](https://spark.apache.org/docs/latest/ml-collaborative-filtering.html)
  * [Book recommendation](https://towardsdatascience.com/building-a-recommendation-engine-to-recommend-books-in-spark-f09334d47d67)
  
<!--* [Example Collaborative Filtering](https://www.tutorialspoint.com/pyspark/pyspark_mllib.htm)
Recommendation with Mlib in Python:
Python/Scala: http://ampcamp.berkeley.edu/5/exercises/movie-recommendation-with-mllib.html
https://medium.com/analytics-vidhya/crafting-recommendation-engine-in-pyspark-a7ca242ad40a
PySpark and MLIB tutorial: https://www.tutorialspoint.com/pyspark/pyspark_mllib.htm
Databrics: https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/3741049972324885/1723574684687027/4413065072037724/latest.html
CollabFiltering with ALS https://towardsdatascience.com/build-recommendation-system-with-pyspark-using-alternating-least-squares-als-matrix-factorisation-ebe1ad2e7679
BookRecommendation: https://towardsdatascience.com/building-a-recommendation-engine-to-recommend-books-in-spark-f09334d47d67 -->

