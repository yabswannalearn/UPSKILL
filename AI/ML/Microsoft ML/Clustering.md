# Clustering[^1]

_Clustering_ is a form of unsupervised machine learning in which observations are grouped into clusters based on similarities in their data values, or features. This kind of machine learning is considered unsupervised because it doesn't make use of previously known label values to train a model. In a clustering model, the label is the cluster to which the observation is assigned, based only on its features.

## Example - clustering

For example, suppose a botanist observes a sample of flowers and records the number of leaves and petals on each flower:

![Diagram of some flowers.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/flowers.png)

There are no known _labels_ in the dataset, just two _features_. The goal is not to identify the different types (species) of flower; just to group similar flowers together based on the number of leaves and petals.

Expand table

|Leaves _(x1)_|Petals _(x2)_|
|---|---|
|0|5|
|0|6|
|1|3|
|1|3|
|1|6|
|1|8|
|2|3|
|2|7|
|2|8|

### Training a clustering model

There are multiple algorithms you can use for clustering. One of the most commonly used algorithms is _K-Means_ clustering, which consists of the following steps:

1. The feature (_**x**_) values are vectorized to define _n_-dimensional coordinates (where _n_ is the number of features). In the flower example, we have two features: number of leaves (_**x1**_) and number of petals (_**x2**_). So, the feature vector has two coordinates that we can use to conceptually plot the data points in two-dimensional space (_**[x1,x2]**_)
2. You decide how many clusters you want to use to group the flowers - call this value _k_. For example, to create three clusters, you would use a _k_ value of 3. Then _k_ points are plotted at random coordinates. These points become the center points for each cluster, so they're called _centroids_.
3. Each data point (in this case a flower) is assigned to its nearest centroid.
4. Each centroid is moved to the center of the data points assigned to it based on the mean distance between the points.
5. After the centroid is moved, the data points may now be closer to a different centroid, so the data points are reassigned to clusters based on the new closest centroid.
6. The centroid movement and cluster reallocation steps are repeated until the clusters become stable or a predetermined maximum number of iterations is reached.

The following animation shows this process:

![Diagram of an animation showing the k-means clustering process.](https://learn.microsoft.com/en-us/training/wwl-data-ai/fundamentals-machine-learning/media/clustering.gif)

### Evaluating a clustering model

Since there's no known label with which to compare the predicted cluster assignments, evaluation of a clustering model is based on how well the resulting clusters are separated from one another.

There are multiple metrics that you can use to evaluate cluster separation, including:

- **Average distance to cluster center**: How close, on average, each point in the cluster is to the centroid of the cluster.
- **Average distance to other center**: How close, on average, each point in the cluster is to the centroid of all other clusters.
- **Maximum distance to cluster center**: The furthest distance between a point in the cluster and its centroid.
- **Silhouette**: A value between -1 and 1 that summarizes the ratio of distance between points in the same cluster and points in different clusters (The closer to 1, the better the cluster separation).

[^1]: Clustering is a way to group similar things together when you don't already know what the groups are. It's like sorting a pile of random stuff into categories based on what looks alike.
	
	**Example:** Imagine you have pictures of different flowers, but you don't know their names. Clustering helps you put the similar-looking flowers into their own groups.
	
	**How it works (K-Means):**
	
	1. Imagine your flower pictures are dots on a map.
	2. You guess how many groups you want (say, 3). Then you randomly pick 3 spots on the map as starting points for your groups. These are like the "centers" of your groups.
	3. Each flower picture gets put into the group whose center is closest to it.
	4. Now, for each group, you find the actual middle spot of all the flower pictures in that group and move the group's center to that new middle spot.
	5. Because the centers moved, some flower pictures might now be closer to a _different_ group's center. So, you re-sort the pictures into the closest groups again.
	6. You keep doing steps 4 and 5 until the groups don't change much anymore.
	
	**How to know if the grouping is good:**
	
	Since you didn't know the flower names to begin with, you can't just check if the groups are "correct." Instead, you look at how well the groups are separated:
	
	- **Are the flowers in each group close to their own group's center?** (Good)
	- **Are the flowers in one group far away from the centers of _other_ groups?** (Good)
	
	Think of it like this: you want each group to be a tight bunch, and you want those bunches to be far apart from each other.
	
