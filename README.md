# Cluster stability

In this project, I compute cluster stability, which is a measure of how similar a clustering on a big data set is to clusterings on subsets of that data set. For example, if a data set of 100,000 nodes yields 10 clusters, would a subset of 1,000 of the nodes yield the same cluster? This is one way to measure how robust a clustering is, and I have implemented it with a simple example in Cluster_stability.ipynb.

The following is a description of the example used, but the functions defined in the ipynb can be used to test the robustness of any clustering of data created from any data set. 

The data given was a set of photos scraped from Instagram pages. Features are extracted from the images using TensorFlow using the VGG16 convolutional neural network (https://neurohive.io/en/popular-networks/vgg16/). Then the features are attempted to be clustered using KMeans clustering. The cluster stability algorithm first applies the clustering to the full data set, then to a large number of randomly chosen subsets of the data. The clusters are mapped to each other using the contingency matrix method. Finally an F1 score is calculated based on how well the new clusters on subsets map back to the original cluster on the full data.

Kmeans produces very robust clusters for fewer than 5 clusters, but AS expected in this example, the stability of the clusters seems to drop suddenly as the number of clusters grows large. 
