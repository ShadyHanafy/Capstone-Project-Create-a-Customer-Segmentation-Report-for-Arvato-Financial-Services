# Customer Segmentation Report for Arvato Financial Services
![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/Arvato-Bertelsmann-Picture.jpg)

## **Project Overview**
This blog purpose is to analyze demographics data for customers of a mail-order sales company in Germany and comparing it against demographics information for the general population to perform customer segmentation, identifying the parts of the population that best describe the core customer base of the company and predict which individuals are most likely to convert into becoming customers for the company. 

The data that you will use has been provided by our partners at Bertelsmann Arvato Analytics, and represents a real-life data science task. I used 10% sample from all the datasets which consists of 4 datasets as follow:
1. Demographics data for the general population of Germany
2. Demographics data for customers of a mail-order company
3. Training Demographics data for individuals who were targets of a marketing campaign
4. Test Demographics data for individuals who were targets of a marketing campaign

## **Problem Statement**
The project work mainly over 3 parts:

***1. Data Pre-processing***
   Analyze, understand, apply data pre-processing techniques over the previous mentioned datasets to cleanup and get them ready for ML models
   
***2. Customer Segmentation***
   Perform customer segmentation and clustering identifying the parts of the population that best describe the core customer base of the company and generate customer segmentation report. I performed feature scaling and applied dimensionality reduction using PCA on the data to find the vectors of maximal variance in the data then apply (Kmeans) to find the optimal number of clusters to represent customers segementation
   
***3. Prediction***
    Predict which individuals are most likely to convert into becoming customers for the company based on another dataset used for this purpose using supervides ML (Logistic Regression) and apply this model on teh training data then on the test data

## **Metrics**

I used "Accuracy Score" which is the most basic diagnostic of a logistic regression which represents the proportion of correct predictions over total predictions

## **Data Exploration**

First, let us have a look at the general population demographics dataset to understand more about its structure and features

 ***Overview of general population demographics dataset***

Sample view for the dataset content

![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/general_sample.png)

***Observations about the dataset***

1. There are 891 211 persons (rows) x 366 features (columns) for the demographics data of the general population of Germany 
2. There are 191 652 persons (rows) x 369 features (columns) for the demographics data for customers of a mail-order company 
3. There are 360 features of numerical values while there are 6 categorical/mixed features for the general population data
4. There are extra features in customers data that I decided to drop to match the general population data structure

## **Data Pre-Processing**
### **Data Cleaning and transforming**

There were around 26 features with missing data more than 40 % of the records of the fearture in the general population data

***Distribution of missing value precent per feature before cleansup***
![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/missing.png)

I took the decision to drop out these columns

***Distribution of missing value precent per feature after cleansup***
![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/final_data.png)

After cleansup the highly missing features we have now around 339 features including the 6 categrical/mixed features. Analyzing those, we can see that 5 of them have multi dimension values so I decided to drop them ['CAMEO_DEU_2015', 'CAMEO_DEUG_2015', 'CAMEO_INTL_2015',
       'D19_LETZTER_KAUF_BRANCHE', 'EINGEFUEGT_AM'] 

![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/categ.png)

As for the last feature ''OST_WEST_KZ' I re-encoded it and convert it to numerical to be used

![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/encode.png)

The last step in this topic I did, is to apply imputaion to fillin the missing values with 'mean' to prepare the data for modeling

***Feature Transformation***
Before I apply dimensionality reduction to the data, I performed feature scaling so that the principal component vectors are not influenced by the natural differences in scale for features. We will use StandardScaler to scale each feature to mean 0 and standard deviation 1. and applied dimensionality reduction using PCA on the data to find the vectors of maximal variance in the data and hence I selected 150 components as represent almost 90% of the variance in the dataset

![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/final_data.png)

For dimensionality reduction I used PCA class to apply principal component analysis on the data to find the vectors of maximal variance in the data. Then we will check the ratio of variance explained by each principal component as well as the cumulative variance explained. Then I plot the cumulative or sequential values to help in selecting a value for the number of transformed features to retain for the clustering part. With the number of components to keep,

![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/pca.png)


## **Customer Segmentation and Clustering**

Based on the PCA visualization, I chose 150 components to retain as they represent almost 90% of the variance in the dataset

Using unsupervised ML technique (Kmeans) I could find the optimal number of clusters to represent customers segementation to be around 15 clusters

![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/clusters.png)

Applying the previous techniques over the customers data and compare the two cluster distributions for the data demographics of the general population and the customer data for a mail-order sales company to see where the strongest customer base for the company is

From the distirbutions its clear that the company's customer base is not universal as the cluster assignment proportions not similar between the two. Its clear that company should target clusters like 14,12 and 15 where customers resides the most and neglect clusters like 3,4,and 8 where customers are least representative

![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/distribution.png)


## **Target Customers Prediction on Train dataset**
The training dataset file included one additional column, "RESPONSE", which indicated whether or not each recipient became a customer of the company where I applied same data pre-rpocessing and cleansup techniques used earlier on the dataset

Generally, to build supervised model we need to split data into training and testing data sets, to build it on the the training data set and to make prediction on the testing data set, however here since we have another test dataset, I split the data into training and validation sets

For the Supervised ML model I used Logistics regression model as its simple model to try out

## **Model Evaluation**
The model accuracy score on the validation data set reaches ~ 97%
![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/score.png)

## **Target Customers Prediction on Test set**
Using the test dataset and applying the built supervised model to get the final outcome

![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/predict.png)

## **Conclusion**
In this project, real-life demographics data of Germany population and demographics data for customers of a mail-order sales company were analyzed. Throughput the project:

***First***: Data pre-processing was done over the datasets, there were 366 columns to analyze and understand their structure. A lot of missing values were identified in the  the features, some were subject to drop the whole feature while others were subject to imputation to fillin the missing values

***Second***: For the customer clustering, the dimensionality reduction using PCA was performed to 150 latent features that describe around 90% of explained variance. KMeans clustering to 15 clusters identified around 3 clusters that can be target customers to the company.

***Lastly***, Logistic Regression technique was used to build supervised model and make predictions over the training and testing datasets. The resulted performance of supervised learning algorithm is 97%.

## **improvements**
There are some improvements can be done here, for example:
***1*** There are other ways to preprocess the data, specially the categorical/mixed data types. 
***2*** Choose another threshold for dropping columns, apply MinMax Scaler instead of Standard Scaler, impute data in another way.

***The detailed data anlysis and all procedures can be found [here](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/Arvato%20Project%20Workbook.ipynb)***
