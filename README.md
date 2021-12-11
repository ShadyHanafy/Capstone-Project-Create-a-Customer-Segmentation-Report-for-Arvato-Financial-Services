
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

For this project, the target is to analyze demographics data for customers of a mail-order sales company in Germany, comparing it against demographics information for the general population. and predict which individuals are most likely to convert into becoming customers for the company. For that purpose we will do the following:

1. Use ETL Pipeline to explore, clean and analyze the data sets
2. Using unsupervised learning techniques to perform customer segmentation, identifying the parts of the population that best describe the core customer base of the company
3. Apply all used techniques on a third dataset with demographics information for targets of a marketing campaign for the company, and use a supervised learning model to predict which individuals are most likely to convert into becoming customers for the company


## File Descriptions <a name="files"></a>

There are 1 notebook and 4 datasets to be used here to showcase work related to the above steps. Markdown cells were used to assist in walking through the thought process for individual steps.  
1. Arvato Project Workbook.ipynb : Include all our work
2. Files to be used (not available for loading)
		* Udacity_AZDIAS_052018.csv: Demographics data for the general population of Germany; 891 211 persons (rows) x 366 features (columns).
		* Udacity_CUSTOMERS_052018.csv: Demographics data for customers of a mail-order company; 191 652 persons (rows) x 369 features (columns).
		* Udacity_MAILOUT_052018_TRAIN.csv: Demographics data for individuals who were targets of a marketing campaign; 42 982 persons (rows) x 367 (columns).
		* Udacity_MAILOUT_052018_TEST.csv: Demographics data for individuals who were targets of a marketing campaign; 42 833 persons (rows) x 366 (columns)


## Results<a name="results"></a>

The main findings of the code can be found at the post available [here](https://github.com/ShadyHanafy/Shady/blob/main/Project%20Details.md).

### FlaskAPP Visualization : http://0.0.0.0:3001/
![This is an image](https://github.com/ShadyHanafy/DisasterResponse.io/blob/main/FlaskApp.png)

# Classification Model Accuracy		
![image](https://github.com/ShadyHanafy/DisasterResponse.io/blob/main/visualize3.png)

## Instructions<a name="instructions"></a>	

Run the following commands in the project's root directory to set up your database and model.

1. To run ETL pipeline that cleans data and stores in database python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/drpdb.db
2. To run ML pipeline that trains classifier and saves python models/train_classifier.py data/drpdb.db models/classifier.pkl
3. Run the following command in the app's directory to run your web app. python run.py
4. Go to http://0.0.0.0:3001/


## Licensing, Authors, Acknowledgements<a name="licensing"></a>

Must give credit to AZ Direct GmbH for the data.  You can find the Licensing for the data and other descriptive information at the link available [here](https://viewbkemtrvpm7.udacity-student-workspaces.com/files/terms.pdf). 
