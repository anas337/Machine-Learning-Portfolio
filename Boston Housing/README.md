[//]: # (Image References)
[image1]: ./Description-Images/Houses.png "image1"
[image2]: ./Description-Images/learning-curves.PNG "image2"
[image3]: ./Description-Images/complexity-curve.PNG "image3"
[image4]: ./Description-Images/Capture.PNG "image4"

# Project: Predicting Boston Housing Prices

## Introduction

The Boston housing market is highly competitive, and you want to be the best real estate agent in the area. To compete with your peers, you decide to leverage a few basic machine learning concepts to assist you and a client with finding the best selling price for their home. Luckily, you\'ve come across the Boston Housing dataset which contains aggregated data on various features for houses in Greater Boston communities, including the median value of homes for each of those areas. Your task is to build an optimal model based on a statistical analysis with the tools available. This model will then be used to estimate the best selling price for your clients\' homes.

![image1]
In this project, I applied basic machine learning concepts on data collected for housing prices in the Boston, Massachusetts area to predict the selling price of a new home. First of all I explored the data to obtain important features and descriptive statistics about the dataset. Next,  I splitted the data into testing and training subsets, and determined a suitable performance metric for this problem.I analyzed performance graphs for a learning algorithm with varying parameters and training set sizes. This facilitated to pick the optimal model that best generalizes for unseen data. Finally, I tested this optimal model on a new sample to compare the predicted selling prices to the previous statistics.

![image2] 
![image3] 

## Install

This project uses the following software and Python libraries:

- [Python 2.7](https://www.python.org/download/releases/2.7/)
- [NumPy](http://www.numpy.org/)
- [pandas](http://pandas.pydata.org/)
- [scikit-learn](http://scikit-learn.org/stable/)
- [matplotlib](http://matplotlib.org/)

You will also need to have software installed to run and execute a [Jupyter Notebook](http://ipython.org/notebook.html).

If you do not have Python installed yet, it is highly recommended that you install the [Anaconda](http://continuum.io/downloads) distribution of Python, which already has the above packages and more included. Make sure that you select the Python 2.7 installer and not the Python 3.x installer.

## Starting the Project

For this project, you can find the `boston_housing` folder containing the necessary project files on the [Machine Learning projects GitHub](https://github.com/anass337/). 

This project contains two files:

- `boston_housing.ipynb`: This is jupyter notebook file which contains python code, visualizations and detailed analysis of each step performed in this project. 
- `boston_housing.html`: An html version of the previous file to facilitate comparison.
- `housing.csv`: The project dataset. You'll load this data in the notebook.
- `README.md` : it contains a short description of this project and steps to run it successfully.

In the Terminal or Command Prompt, navigate to the folder containing the project files, and then use the command `jupyter notebook boston_housing.ipynb` to open up a browser window or tab to work with your notebook. Alternatively, you can use the command `jupyter notebook` or `ipython notebook` and navigate to the notebook file in the browser window that opens. A **README** file has also been provided with the project files which may contain additional necessary information or instruction to run the project successfully

## Run

In a terminal or command window, navigate to the top-level project directory `boston_housing/` (that contains this README) and run one of the following commands:

```bash
ipython notebook boston_housing.ipynb
```  
or
```bash
jupyter notebook boston_housing.ipynb
```

This will open the Jupyter Notebook software and project file in your browser.

## Data

The modified Boston housing dataset consists of 489 data points, with each datapoint having 3 features. This dataset is a modified version of the Boston Housing dataset found on the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Housing).

**Features**
1.  `RM`: average number of rooms per dwelling
2. `LSTAT`: percentage of population considered lower status
3. `PTRATIO`: pupil-teacher ratio by town

**Target Variable**
4. `MEDV`: median value of owner-occupied homes
![image4] 