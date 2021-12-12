# Customer Segmentation Report for Arvato Financial Services
![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/Arvato-Bertelsmann-Picture.jpg)

This blog purpose is to analyze demographics data for customers of a mail-order sales company in Germany, comparing it against demographics information for the general population. and predict which individuals are most likely to convert into becoming customers for the company, I will use CRISP-DM to:

1. Analyze and understand the general deographics and customers data sets
2. Perform customer segmentation and clustering identifying the parts of the population that best describe the core customer base of the company and generate customer segmentation report
3. Predict which individuals are most likely to convert into becoming customers for the company based on another dataset used for this purpose

## **DATA**

In this project I used the datasets from AZ Direct GmbH provided to Udacity project. For all used datasets and analysis I used sample of 10% for ease of implementation

## **Data Understanding**

First, let us have a look at the general population demographics dataset to understand more about its structure and features

## **Overview of general population demographics dataset**

Sample view for the dataset content

![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/general_sample.png)

## **Observations about the dataset**

1. There are 891 211 persons (rows) x 366 features (columns) for the demographics data of the general population of Germany 
2. There are 191 652 persons (rows) x 369 features (columns) for the demographics data for customers of a mail-order company 
3. There are 360 features of numerical values while there are 6 categorical/mixed features for the general population data
4. There are extra features in customers data that I decided to drop to match the general population data structure
5. There are around 26 features with missing data more than 40 % of the records of the fearture in the general population data

After data preparation and cleansing, now let's try to answer the above questions

## **Analysis Findings**
### **Data Cleaning and transforming**

![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/final_data.png)

1. After cleansup the highly missing features we have now around 339 features including the 6 categrical/mixed features. Analyzing those, we can see that 5 of them have multi dimension values so I decided to drop them ['CAMEO_DEU_2015', 'CAMEO_DEUG_2015', 'CAMEO_INTL_2015',
       'D19_LETZTER_KAUF_BRANCHE', 'EINGEFUEGT_AM'] while for the last feature ''OST_WEST_KZ' I re-encoded it and convert it to numerical to be used

2. I performed feature scaling and applied dimensionality reduction using PCA on the data to find the vectors of maximal variance in the data and hence I selected 150 components as represent almost 90% of the variance in the dataset

![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/pca.png)


### **Customer Segmentation and Clustering**

1. Using unsupervised ML technique (Kmeans) I could find the optimal number of clusters to represent customers segementation to be around 15 clusters
![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/clusters.png)

2. Applying the previous techniques over the customers data and compare the two cluster distributions for the data demographics of the general population and the customer data for a mail-order sales company to see where the strongest customer base for the company is

3. From the distirbutions its clear that the company's customer base is not universal as the cluster assignment proportions not similar between the two. Its clear that company should target clusters like 14,12 and 15 where customers resides the most and neglect clusters like 3,4,and 8 where customers are least representative
![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/distribution.png)


### **Target Customers Prediction**

1. Using a dataset of 42 982 persons (rows) x 367 (columns) represent demographics data for individuals who were targets of a marketing campaign for training purpose
2. The training dataset file included one additional column, "RESPONSE", which indicated whether or not each recipient became a customer of the company
3. Using Supervised ML model (Logistics regression) we could build a prediction model for that purpose with training accuracy ~ 97%
4. Using a dataset of 42 833 persons (rows) x 366 (columns) represent demographics data for individuals who were targets of a marketing campaign for testing purpose for the model
![This is an image](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/predict.png)
