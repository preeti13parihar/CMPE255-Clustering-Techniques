# CMPE255-Clustering-Techniques
Using various clustering techniques

# **Use various clustering techniques**
## **Dataset - Yelp Restaurants**

About - From the Business Objects, I tried to find food related areas in Portland city. These are characterized by closeness and similarity of restaurants. Used the "longitude" and "latitude" to cluster closeness. Used "categories" to cluster for similarity.

Found clusters using the following techniques
* **K-Means from scratch**
* **Hierarchical**
* **Gaussian Mixture Model**
* **DBSCAN**

I parsed the data from the json file to a pandas dataframe. The final dataframe used for clustering has a total of 17 columns. Two of which are latitude and longitude and the remaining 15 are the columns of top15 categories of Restaurants in Portland city. If a category is present for a restaurant then its value for that column is 1.0 or else 0.I performed feature scaling on latitude and longitude by subtracting the mean of the entire column from each value and then dividing by the standard deviation (Also known as Z-score), thus scaling down the location to the range of categories.

# **Comments**

I used complete link method for heirarchical clustering i.e finding the distance between the two points farthest from each other in order to combine clusters during the agglomerative clustering method. 

Performed GMM using co-variance as 'spherical' so that each component has its own single variance.


I calculated the ratio of each category present in the cluster with the total number of restaurants in Portland city of that category. And then selected the category having a maximum ratio as the label for that particular cluster. Thus, avoiding dominance by a particular category having large number of restaurants. Below is the interpretation of the results of the methods used.

**K-means**: K-means has more well-defined clusters because it does hard-clustering i.e. each point belongs to one and only one cluster. also, since the function used is kmeans, the initial points are calculated based on a probability function.

**Hierarchical**: Since it considers each point as a cluster on its own and then combines the points on the basis of distance between the points. It gives a result which varies quite a lot from the K-means method since it does not use any random points.

**Gaussian Mixture Model**: GMM uses soft-clustering and hence has overlapping clusters.It calculates the probability of a point belonging to each cluster and hence is more likely to give better clustering. It gives clustering similar to K-means but with some overlapping points.

**DBSCAN**: **DBSCAN** fits the model on the training dataset and predicts a cluster for each example in the dataset. A scatter plot is then created with points colored by their assigned cluster.
