# Option 3 Clustering - Looking at FDA food descriptions
[Assignment and Starter Code](https://github.com/visualizedata/ml/tree/master/final_assignment_3/option_3)

This assignment works with k-means clustering. It aims to group FDA food recalls based on the text description of the item and the recall. Since text is the primary feature, a bag of words feature
set is used to build the initial feature matrix to pass to the k-means model. I did investigate using the TruncatedSVD method to streamline the feature set, but found that it was overfitting the clusters. Specifically, the three clusters consisted of two very small and specific groups and one
catch-all. See the following screenshot of one of the small clusters:
![small cluster](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-1/svd_cluster2.PNG)

For the k-means model, I used the elbow plot to identify the number of clusters. Looking at 50 clusters and then again at 10, there seemed to be a clear elbow at 3. 
![elbow](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-1/clusters50.png)
Moving forward with 3 clusters, I felt that the groups were still too broad for my liking (salmon with fruit doesn't quite fit). Next steps will be to run the elbow plot for a much larger
number of clusters to see if there is a more prominent elbow.
![3 clusters](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-1/3clusters_1.PNG)
