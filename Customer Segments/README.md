[//]: # (Image References)
[image1]: ./Description-Images/customer-segments.jpg "image1"
[image2]: ./Description-Images/heat-map.bmp "image2"
[image3]: ./Description-Images/scatter-matrix.bmp "image3"
[image4]: ./Description-Images/pca.bmp "image4"
[image5]: ./Description-Images/biplot.bmp "image5"
[image6]: ./Description-Images/clustering.bmp "image6"

# Content: Unsupervised Learning
## Project: Creating Customer Segments
![image1]
## Project Overview: 

A wholesale distributor recently tested a change to their delivery method for some customers, by moving from a morning delivery service five days a week to a cheaper evening delivery service three days a week. Initial testing did not discover any significant unsatisfactory results, so they implemented the cheaper option for all customers. Almost immediately, the distributor began getting complaints about the delivery service change and customers were canceling deliveries, losing the distributor more money than what was being saved. 

As a Machine Learning Engineer, i should find what types of customers they have to help them make better, more informed business decisions in the future. The task achieved by the end of this project is to use unsupervised learning techniques to see if any similarities exist between customers, and how to best segment customers into distinct categories. 

In this project we applied unsupervised learning techniques on product spending data collected for customers of a wholesale distributor in Lisbon, Portugal to identify customer segments hidden in the data. First of all, I explored the data by selecting a small subset to sample and determine if any product categories highly correlate with one another. Afterwards, I preprocessed the data by scaling each product category and then identifying (and removing) unwanted outliers. 
![image2]
With the good, clean customer spending data, I applied PCA transformations to the data and implemented clustering algorithms to segment the transformed customer data. Finally, I had compared the segmentation found with an additional labeling and consider ways this information could assist the wholesale distributor with future service changes.
![image4]
![image6]
## Software Requirements

This project requires **Python 2.7** and the following Python libraries installed:

- [Python 2.7](https://www.python.org/download/releases/2.7/)
- [NumPy](http://www.numpy.org/)
- [Pandas](http://pandas.pydata.org/)
- [scikit-learn](http://scikit-learn.org/stable/)
- [matplotlib](http://matplotlib.org/)

You will also need to have software installed to run and execute an [iPython Notebook](http://ipython.org/notebook.html)

We recommend to install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 

## Starting the Project

For this project, you can find the `customer_segments` folder containing the project files on the [Machine Learning Portfolio]((https://github.com/anas337/Machine-Learning-Portfolio) repository.

This project contains four files and one directory:

- `customer_segments.ipynb`: This a jupyter notebook file which contains code and clustering analysis.
- `customer_segments.html`: An html version of the previous file.
- `customers.csv`: dataset will be loaded in the notebook
- `README.md`.
- `Description-Images (Directory)`: it contains some images used for esthetics purposes.

### Run

In a terminal or command window, navigate to the top-level project directory `customer_segments/` (that contains this README) and then use the command `jupyter notebook customer_segments.ipynb` to open up a browser window or tab to use the notebook. Alternatively, you can use the command `jupyter notebook` or `ipython notebook` and navigate to the notebook file in the browser window that opens. 

you can run one of the following commands:

```bash
ipython notebook customer_segments.ipynb
```  
or
```bash
jupyter notebook customer_segments.ipynb
```

This will open the Jupyter Notebook software and project file in your browser.

## Data

The customer segments data is included as a selection of 440 data points collected on data found from clients of a wholesale distributor in Lisbon, Portugal. More information can be found on the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Wholesale+customers).

Note (m.u.) is shorthand for *monetary units*.

**Features**
1) `Fresh`: annual spending (m.u.) on fresh products (Continuous); 
2) `Milk`: annual spending (m.u.) on milk products (Continuous); 
3) `Grocery`: annual spending (m.u.) on grocery products (Continuous); 
4) `Frozen`: annual spending (m.u.) on frozen products (Continuous);
5) `Detergents_Paper`: annual spending (m.u.) on detergents and paper products (Continuous);
6) `Delicatessen`: annual spending (m.u.) on and delicatessen products (Continuous); 
7) `Channel`: {Hotel/Restaurant/Cafe - 1, Retail - 2} (Nominal)
8) `Region`: {Lisbon - 1, Oporto - 2, or Other - 3} (Nominal) 


![image3]

![image5]