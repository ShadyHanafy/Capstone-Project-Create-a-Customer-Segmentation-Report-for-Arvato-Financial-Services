
### Table of Contents

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [File Descriptions](#files)
4. [Results](#results)
5. [Instructions](#instructions)
6. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation <a name="installation"></a>

The code should run with no issues using Python versions 3. The libraries to run the code here beside the Anaconda distribution of Python as as follow:
* numpy
* pandas
* sns
* matplotlib
* sklearn

## Project Motivation<a name="motivation"></a>

For this project, the target is to analyze demographics data for customers of a mail-order sales company in Germany, comparing it against demographics information for the general population and predict which individuals are most likely to convert into becoming customers for the company. For that purpose we will do the following:

1. Use ETL Pipeline to explore, clean and analyze the data sets
2. Using unsupervised learning techniques to perform customer segmentation, identifying the parts of the population that best describe the core customer base of the company
3. Apply all used techniques on a third dataset with demographics information for targets of a marketing campaign for the company, and use a supervised learning model to predict which individuals are most likely to convert into becoming customers for the company


## File Descriptions <a name="files"></a>

There are 1 notebook and 4 datasets to be used here to showcase work related to the above steps. Markdown cells were used to assist in walking through the thought process for individual steps.  
1. Arvato Project Workbook.ipynb : Include all our work
2. Files to be used (not available for loading):

		* Udacity_AZDIAS_052018.csv: Demographics data for the general population of Germany; 891 211 persons (rows) x 366 features (columns).
		
		* Udacity_CUSTOMERS_052018.csv: Demographics data for customers of a mail-order company; 191 652 persons (rows) x 369 features (columns).
		
		* Udacity_MAILOUT_052018_TRAIN.csv: Demographics data for individuals who were targets of a marketing campaign; 42 982 persons (rows) x 367 (columns).
		
		* Udacity_MAILOUT_052018_TEST.csv: Demographics data for individuals who were targets of a marketing campaign; 42 833 persons (rows) x 366 (columns)


## Results<a name="results"></a>

The main findings & results have been clearly documented in the Jupyter Notebook. Please refer [here](https://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/Arvato%20Project%20Workbook.ipynb).

## Licensing, Authors, Acknowledgements<a name="licensing"></a>

Must give credit to AZ Direct GmbH for the data.  You can find the Licensing for the data and other descriptive information at the link available [here](hhttps://github.com/ShadyHanafy/Customer-Segmentation-Report-for-Arvato/blob/main/Project_Details.md). 
