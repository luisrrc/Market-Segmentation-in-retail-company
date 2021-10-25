![Python](https://img.shields.io/badge/Python-blue)
![Framework](https://img.shields.io/badge/Framework-Tensorflow-orange)
![Frontend](https://img.shields.io/badge/Plotly-yellow)
![Frontend](https://img.shields.io/badge/Sklearn-green)


**Note** - for a better visualization of the notebook and the different charts click here: https://deepnote.com/project/Market-Segmentation-2irPBoppSnuxnimiY8kdyQ/%2FMarket_Segmentation.ipynb

```
└── Market Segmentation Analysis
    ├── Importing Libraries and Dataset
    ├── Data Cleaning & EDA
    ├── Applying Elbow Method
    ├── Autoencoder
    ├── k-Means algorithm
    └── PCA
```

# Market Segmentation in Retail

## Business Understanding

A retail company in the US wants to develop a marketing campaign. The company has data on their customers for about almost 3 years, so they need to create a targeted ad marketing campaign by dividing their customers into at least 3 distinctive groups. This is a unsupervised machine learning case.

## Data

The Dataframe is made up of the following features:

**ORDERNUMBER** = identification of order placed.

**QUANTITYORDERD** = number of items ordered.

**PRICEEACH** = price of each item.

**MSRP** = is the manufacturer's suggested retail price (MSRP). 

**DEALSIZE** = size of the order.

**SALES** = total amount of sales.

**ORDERDATE** = date in which order is placed.

**STATUS** = status of the order.

**QTR_ID** = quarter in which order is placed.

**MONTH_ID** = month in which order is placed.

**YEAR_ID** = year in which order is placed.

**PRODUCTLINE** = product category.

**CUSTOMERNAME** = name of the customer.

**PHONE** = phone number.

**ADDRESSLINE1** = address to be shipped.

**ADDRESSLINE2** = address to be shipped.

**CITY** = city in which customer resides.

**STATE** = state in which customer resides.

**POSTALCODE** = postal code in which customer resides.

**COUNTRY** = country in which customer resides.

**TERRITORY** = territory in which customer resides.

**CONTACTFIRSTNAME** = contact person's first name.

**CONTACTLASTNAME** = contact person's last name.

## Exploratory Data Analysis and Data Cleaning

1) After examining the "country" column, we can see that most of the customers reside in the Usa, Spain and France.
2) We drop the column STATUS because its too imbalanced.
3) A function is created to add dummy variables to replace the values of the categorical variables.
4) We can see from the line graph, the peaks in sales are reached in the month of November.
5) A trend exists between 'SALES' and 'QUANTITYORDERED'.
6) A trend exists between 'MSRP' and 'PRICEEACH'.
7) A trend exists between 'PRICEEACH' and 'SALES'.


## Apply the Elbow Method to find the optimal number of clusters
**The Elbow Method**  is an empirical method to find out the best value of k. It picks up the range of values and takes the best among them. It calculates the sum of the square of the points and calculates the average distance. When the value of k is 1, the within-cluster sum of the square will be high. As the value of k increases, the within-cluster sum of square value will decrease.

Finally, we will plot a graph between k-values and the within-cluster sum of the square to get the k value, we will examine the graph carefully. At some point, our graph will decrease abruptly. That point will be considered as a value of k.

![62725cluster0](https://user-images.githubusercontent.com/58336896/138468660-9cf2c5a6-5be1-41b9-a59a-e9df00fe3de5.png)

After apply the elbow method, the value of K is: 3

![elbow method](https://user-images.githubusercontent.com/58336896/138717417-153db571-a746-4f8c-9ddb-301b59d8d0f0.png)

source: https://www.analyticsvidhya.com/blog/2021/05/k-mean-getting-the-optimal-number-of-clusters/

## K-Means Algorithm

K-Means clustering intends to partition n objects into k clusters in which each object belongs to the cluster with the nearest mean. This method produces exactly k different clusters of greatest possible distinction. The best number of clusters k leading to the greatest separation (distance) is not known as a priori and must be computed from the data. The objective of K-Means clustering is to minimize total intra-cluster variance, or, the squared error function: 

![Clustering_kmeans_c](https://user-images.githubusercontent.com/58336896/138462797-1c66a5a6-a827-4610-a70f-7e871f2ce363.png)

K-Means algorithm steps:

1- Clusters the data into k groups where k  is predefined.

2- Select k points at random as cluster centers.

3- Assign objects to their closest cluster center according to the Euclidean distance function.

4- Calculate the centroid or mean of all objects in each cluster.

5- Repeat steps 2, 3 and 4 until the same points are assigned to each cluster in consecutive rounds.

source: https://www.saedsayad.com/clustering_kmeans.htm

After apply the k-means algorithm to the data using the value of k = 3, these are the results:

![clusters](https://user-images.githubusercontent.com/58336896/138717659-25b90d86-6570-49e8-ac73-7bbbfa7e96f8.png)




## Applying Principal Component Analysis (PCA)

What is PCA?

PCA is a very effective dimensionality reduction technique that achieves dimensionality reduction without compromising on the information content of the data. The basic idea behind PCA is to first identify correlations among different variables within the dataset. Once correlations are identified, the algorithm decides to eliminate the variables in such a way that the variability of the data is maintained. In other words, PCA aims to find uncorrelated sources of data.

After apply PCA for dimensionality reduction, we can visualize the clusters using a 3-D Scatter plot:

![xcatter plot](https://user-images.githubusercontent.com/58336896/138718702-147aa3e7-5a59-4fa4-a4c5-68ed70c7fc5d.png)

## Autoencoder

![Autoencoders-graph](https://user-images.githubusercontent.com/58336896/138476513-ad704545-fbe2-4ffb-9f8b-09140cbbcba2.png)
source: https://neptune.ai/blog/autoencoders-case-study-guide
