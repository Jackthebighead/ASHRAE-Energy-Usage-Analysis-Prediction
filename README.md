# ASHRAE-Energy-Usage-Analysis-System

`Author: YUAN Yan Zhe`

This is the term project of MSBD5003 Big Data Computing course, a spark based energy usage analysis system on ASHRAE system.



### Project Introduction

In this project, a energy consumption system based on ASHRAE energy dataset is implemented using Spark technology. The project architecture diagram is shown below:

![Aaron Swartz](https://github.com/Jackthebighead/ASHRAE-Energy-Usage-Analysis-Prediction/blob/master/assets/image-20201205171331511.png)

To be specific, this project contains two parts: 

- **Exploratory Data Analysis**: Data mining and visualization on the dataset. Both spark and pandas way are performed.
  - Spark DataFrame
  - RDD
  - Spark SQL
  - Pandas
  - Matplotlib
  - Seaborn
  - Plotly
- **Preditions**: Predicting the meter_reading on year 2017&2018. Prediction using machine learning methods. Both spark and sklearn/tf way are performed.
  - Spark Mllib:
    - Linear Regression
    - Random Forest
    - Gradient Boosting Tree
    - Decision Tree
  - Sklearn, LGBM, and tensorflow.

### Notes on File Sestem & Reproduction

- This project focus on the Spark implementation rather than prediction results.

- Data set download can be download via: https://www.kaggle.com/c/ashrae-energy-prediction/data, or through command:  `kaggle competitions download -c ashrae-energy-prediction`.

- The spark part runs totally on Azure Databricks Service.

- Data and intermediate results are stored in MongoDB cluster on MongoDB Atlas and Databricks DBFS (due to the limited storage of our MongoDB cluster). 

  - you can change the data storage architecture according to your own resources.

- File System Intro:

  - `data_connector.ipynb`

    - this module is designed for data preprocessing of raw data, and transfer local data to local MongoDB using pymongo.

    - can be run locally.

  - eda
    - `eda_databricks.ipynb`
      - Spark based eda
    - `eda_pd_local.ipynb`
  - model_spark 
    - all runs in **Azure Databricks**
  - model_comparison
    - run locally. implemented using packages like sklearn/lgbm/tf
  - `submittor.ipynb`
    - transfer to submission file on kaggle

- How to do reproduction:
  - EDA: Run corresponding ipynb in eda on Databricks/local system.
  - Predictions: 
    - Run `data_connector_for_databricks` to store data in databases
    - Run `data_preprocessing.ipynb` to create intermediate result for predictions.
    - Run all predictions file to perform predictions.lol
    - Run`submittor.ipynb`
  - Model_comparison contains several methods apart from spark.mllib. They can be run locally.

### Future Work

- Systemerization
  - A Flask based web dashboard is developing
  - Deployment through Azure App Service





