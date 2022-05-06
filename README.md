# Customer Churn Prediction in OTT Platforms
* This project repository is created in partial fulfillment of the requirements 
for the Big Data Analytics course offered by the Master of Science in Business Analytics 
program at the Carlson School of Management, University of Minnesota <br>
* The project was collaborated with Yi Fang, Sridhar Iyer, Jayadev KP, Yufan Li, and Chandra Mouli Kambhampati

# Executive Summary 
The OTT platforms in the United States have seen tremendous growth in the past couple of years. The United States OTT Market is expected to register a CAGR of approximately 11.22% in terms of revenue and approximately 2.25% in terms of subscribers over the forecast period (2021-2026). The Covid-19 has exacerbated an already intensifying shift from cable to digital. The entertainment industry is shifting from TV and pay-per-view to subscription-based content viewing experiences.

But there is intensifying competition too. In the past year alone, more than 300 new subscription-based media companies have joined the OTT market. Everyone from news companies to lifestyle companies is introducing OTT platforms. The market is heading towards gradual consolidation. Therefore, user numbers are one of the most critical metrics to these OTT platforms in this competitive landscape. There are already signs of saturation in signing new customers, and customer attention is also dropping due to media fatigue. High churn has had OTT platforms scrambling to retain customers by offering higher personalization and incentives. Platforms that have taken a proactive data-backed approach toward customer retention have enjoyed comparatively lower churn rates (e.g., Netflix).

**Our project aims to leverage big data technologies coupled with machine learning to help OTT platforms predict churn at a customer level in real-time.** This would help their customer engagement teams take timely action. We have also constructed a real-time dashboard that can help them understand churn by geography, subscriber type, and other metrics. We have primarily leveraged Amazon S3 as the data storage, Databricks for data processing, spark MLlib for machine learning, and Amazon Quicksight for visualization. We further envision that this setup can be leveraged to assist in personalization and AB testing.

# Project Description
The objective of this project is to predict “customer churn” which is if a listener is likely to cancel their subscription. Our goal is to identify these customers via their interactions with the website. The dataset contains 18 features which can be used to predict the probability of churn. 

# Project Process
![alt text](https://github.com/evelyncy96/Customer_Churn_Prediction_Using_PySpark/blob/main/Project%20Structure%20%26%20EDA/Project%20Process.jpeg)


# Data description: 
This is a public dataset named Million Song Dataset and can be downloaded under json format prepared by Udacity. It contains 18 columns which have the information of customers(gender, name, etc.) and API events(login, playing next song, etc.) The experiment period is from 2018–10–01 to 2018–12–01. The data set is a 12 GB user log data which is hosted on a AWS S3 repository.  

## To access the dataset:
Dataset is available on S3 and can be accessed as below:

#### Step1: Create spark session
spark = SparkSession \
         .builder \
         .appName("Sparkify") \
         .getOrCreate()

#### Step2: Read in sparkify dataset
full_data = "s3n://udacity-dsnd/sparkify/sparkify_event_data.json"<br>
mini_data = "s3n://udacity-dsnd/sparkify/mini_sparkify_event_data.json"

df = spark.read.json(full_data)

## EDA for the dataset through dasboard
![alt text](https://github.com/evelyncy96/Customer_Churn_Prediction_Using_PySpark/blob/main/Project%20Structure%20%26%20EDA/Dashboard.jpeg)


# Target audience
The target audience of our analysis would be digital music service firms and their stakeholders who would be interested in preventing customer churn. 

# Big Data Tools Used
Ingestion, ETL, exploration, Analysis: AWS S3, Databricks(Spark)<br>
Visualization: AWS quicksight

# Instructions to run the scripts
* **Sparkify_code.ipynb** is the first script that needs to be run. This script performs the **data pre-processing, feature engineering & model building**.<br> 
* **Stream.ipynb** is the second script that has to be run. It assumes that the customer churn model is already built from the previous script & **implements streaming analysis** using the churn model.

# Reference
1.https://github.com/CapAllen/Sparkify<br>
2.https://medium.com/@olivier.klein/sparkify-udacity-data-scientist-nanodegree-capstone-project-65e3181ea2b0<br>
3.https://github.com/Tselmeg-C/Churn_prediction_Udacity_Capstone<br>
4.https://www.brid.tv/ott-statistics-for-2021-infographic/<br>
5.https://www.statista.com/outlook/amo/media/tv-video/ott-video/worldwide<br>
6.https://www.parksassociates.com/blog/article/pr-12152021<br>
7.https://dazeinfo.com/2021/09/22/adoption-of-ott-in-us-over-82-million-households-streamed-ott-content-june-2021/



