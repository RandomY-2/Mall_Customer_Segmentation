# Mall_Customer_Segmentation
 
## Description

In this notebook, I made an exploratory data analysis and a clustering of customers using **K-Means Algorithm** on Kaggle's [Mall Customer Segmentation dataset](https://www.kaggle.com/vjchoudhary7/customer-segmentation-tutorial-in-python). Specifically, I 

 - analyzed the **general shape and columns** of the dataset,
 - made **univariate data analysis with 4 customer-related columns** to find the distribution of age, income, gender, and spending score of customers, 
 - used bivariate data analysis to **visualize the relationships between the 4 columns and select 2 relationships that show clusters**, and 
 - **clustered customers based on their ID, annual income, and spending score** using K-Means algorithm. 
 
## EDA Samples

Here are some of the properties of the data I looked at for my EDA. 

- Gender Distribution of Customers
<p align="left">
  <img width="800" height="600" src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/gender_distribution.jpg">
</p>

- Age Distribution of Customers
<p align="left">
  <img width="800" height="500" src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/age_distribution.jpg">
</p>

<p align="left">
  <img width="800" height="500" src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/age_boxplot.jpg">
</p>
 
<p align="left">
  <img width="800" height="250" src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/age_info.jpg">
</p>

- Income Distribution of Customers
<p align="left">
  <img width="800" height="500" src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/income_distribution.jpg">
</p>

<p align="left">
  <img width="800" height="500" src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/income_boxplot.jpg">
</p>
 
<p align="left">
  <img width="800" height="250" src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/income_info.jpg">
</p>

For the distribution of income, the boxplot further shows there are outliers. Thus I also took a look at the outlier customers.

<p align="left">
  <img src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/income_outlier.jpg">
</p>

There are actually two customers who make 137K per year, and their customer ID, gender, and age are also very similar. However, an interesting fact is that their spending scores are very different, almost on the two side of the score spectrum! This is very strange, because normally one may think that if someone has a high annual income, he will buy more things from the mall, which thus assigns the customer a high spending score.

<br>

- Spending Score Distribution of Customers

<p align="left">
  <img src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/score_distribution.jpg">
</p>

- Pairplots

<p align="left">
  <img width="800" height="500" src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/pairplots.jpg">
</p>

## Clustering

From the pairplot, it shows that there seems to be clusters for Customer ID vs. Spending Score graph and Annual Income vs. Spending Score graph. Thus I am curious if the algorithm will form five clusters for these features as I predict. 

### Customer ID vs. Spending Score

Before we make the clustering, let's see the scatterplot one more time.

<p align="left">
  <img width="800" height="500" src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/customer_score.jpg">
</p>

The graph clearly shows five clusters, which are customers with 1). low Customer ID and high Spending Score, 2). low Customer ID and low Spending Score, 3). medium Customer ID and medium Spending Score, 4). high Customer ID and high Spending Score, and 5). high Customer ID and low Spending Score.

Using K-Means with 5 clusters, the output of the algorithm is as follows:

<p align="left">
  <img src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/customer_score_clustering.jpg">
</p>

We can see that the algorithm successfully makes the 5 clusters, although some customers with medium ID and medium Spending Score seem to be grouped with the customers with low ID and high Spending Score.

### Annual Income vs。 Spending Score

Again, let's see the scatterplot one more time.

<p align="left">
  <img src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/income_score.jpg">
</p>

The scatterplot also shows the five clusters. Using K-Means with 5 clusters on these two features, the output is:

<p align="left">
  <img src="https://github.com/RandomY-2/Mall_Customer_Segmentation/blob/main/images/income_score_clustering.jpg">
</p>

Which is again meeting our expectation. Moreover, on this distribution the K-Means seem to not grouping part of the middle group with the top left customers. 
