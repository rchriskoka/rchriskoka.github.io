---
title: "Data Engineering Projects"
date: 2019-12-07
tags: [ETL Pipeline, Batch Processing, Stream Processing]
header:
  image: "/images/back.jpeg"
excerpt: "Data Engineering"
mathjax: "true"
---

# Overview of Projects

### Project 1: Downloading, Reading and Filtering Data
**Project Description:** This project covered the fundamentals of reading downloading data from a source, reading the data and uploading the data into a data store. This is the fundamentals of Data Engineering, building a simple Extract, Load and Transform Pipeline (ETL).

Python code block:
```python
    import boto3
    import pandas as pd 

    def main():
      #Utilizing our s3 resource
      s3 = boto3.client('s3')
      bucket_name = 'blossom-data-eng-richmond'
```

Click [here](https://github.com/rchriskoka/Data-Engineering-Blossom/tree/master/project1) to view this project.


### Project 2: Batch Processing For Data Mining
**Project Description:**  This project investigates top keywords companines within various cities in the USA require data science candidates to have in their resumes. 
Project used PySpark to process the data and also implemented Natural Language Processing Fundamentals.

Python code block:
```python
    import pyspark
    import boto3
    import os
    from pyspark import SparkContext

    #Create Spark Session
    spark = SparkSession.builder.getOrCreate()

    #Initialize s3 resource
    s3 = boto3.client('s3')

    #Import NGRAM and Tokenizer
    from pyspark.ml.feature import NGRAM, Tokenizer
```
Click [here](https://github.com/rchriskoka/Data-Engineering-Blossom/tree/master/project2) to view see more on this project.


### Project 3: Basic End-To-End Extract Transform Load (ETL) Pipeline
**Project Description:** This project covered intermediate concepts of Extract, Transform and Load. Spark was used in processing the data and then manipulating the data after processing was done with PostgreSQL.


Python code block:
```python
    import pyspark
    from pyspark.sql import SparkSession
    from pyspark.sql.types import BooleanType

    #Data Extraction
    answers = spark.read.csv("/answers.csv", header=True, inferSchema=True)

```

Click [here](https://github.com/rchriskoka/Data-Engineering-Blossom/tree/master/project3) to see more on this project.



### Project 4: Scraping Real Estates Listings From Meqasa
This project implements the concept of web scraping which is simply to automatically mine data or collect information from a specific source (website) using certain tools. 
In this project, real estates listings were scrapped from a website involved in real estates. 


Python code block:
```python
    import re 
    from bs4 import BeautifulSoup
    import requests

    #Download data from webpage
    meqasa = requests.get("https://meqasa.com/properties-for-sale-in-ghana")

    #Store the page with the parser in a soup
    soup = BeautifulSoup(meqasa.content, 'lxml')

```

Click [here](https://github.com/rchriskoka/Data-Engineering-Blossom/tree/master/project4) to view more on this project.

### Project 5: Streaming Processing From Loop Ghana
**Project Description:** This projects goes a step further to illustrate the concepts of stream processing. Thid projects scrapes data from a real estates website (Loop Ghana) and stores listings into a csv file in real time. 
Anytime listings are updated, this information will be extracted and stored into the csv file created. Kinesis was the main package used in this project.


Python code block:
```python
    import numpy as np
    import datetime as dt 
    import pandas as pd 

    #Initiate the kinesis 
    kinesis = boto3.client('kinesis', region_name='us-east-2')

    
```


Click [here](https://github.com/rchriskoka/Data-Engineering-Blossom/tree/master/project5) to view more on this project.


