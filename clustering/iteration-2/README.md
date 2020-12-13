# Final Iteration

## Option 3 Clustering - Looking at FDA food descriptions
[Assignment and Starter Code](https://github.com/visualizedata/ml/tree/master/final_assignment_3/option_3)

### Features
This assignment works with k-means clustering. It aims to group FDA food recalls based on the text description of the item and the recall. Since text is the primary feature, a bag of words feature
set is used to build the initial feature matrix to pass to the k-means model. In the [first iteration](https://github.com/amina-brown/machine-learning/tree/master/clustering/iteration-1), I investigated using the TruncatedSVD metho, but ultimately decided it was 
not beneficial. For this round, I made many changes to the feature representation as it seemed to be the best way to affect change on the results. I tested many different approached including the following: 
- Removing all numbers
- Shortening the strings to be the first 100 characters
- Switching from CountVectorizer to HashingVectorizer

The final feature set uses HashingVectorizer, removes all "common" words (from NLTK package) and some words that were common in the data set, but not included in the default "common" words list.
The additional common words were identified using the Counter() function in the collections package and the final list is below:

``common=['oz','lb','lbs','product','packaged','code','brand','upc','packed','sold','distributed','net','wt','g','inc','item','labeled','label','ca','llc','date','bag','bags','weight','case','container','plastic','per','size','individually','containers','kg','film']``

### Number of Clusters
For the k-means model, I initially used the elbow plot to try to identify the number of clusters. This proved to be unhelpful, with no clear elbow appearing during any iterations (see example output below).
![elbow](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-1/clusters50.png)

After deciding to not use the elbow plot, I choose to use the silhouette plots to help make decisions about how many clusters to choose. This also provided me with insight into how the size and specificity of the clusters are correlated. In general, you can see that the larger clusters tend to have lower coefficient values.
I ran plots for a many numbers of clusters, and while the higher the number, the higher the avg coefficient, I decided that from a users perspective, having too many clusters could be overwhelming. I also realized that this would mean that while some clusters were spot on, others were quite the opposite, and could lead to too much inconsistency in what to expect.
See some sample silhouette plots here: 
![5](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-2/images/silhouette5.png)
![25](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-2/images/silhouette25.png)
![50](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-2/images/silhouette50.png)

With this information in mind, I decided to look into using 5 clusters, assuming that you could reasonably split a grocery store into that many groups (produce, meats/cheeses, frozen foods, dry goods, misc.). The resulting clusters were quite non-sensical, so I quickly abandoned this idea.
This led to looking to use 10-15 clusters to emmulate the number of aisles in an average grocery store. Ultimately, I decided on using 15 since it provided a slightly higher avg coefficient without being too overwhelming.
The final silhouette plot is here:
![final](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-2/images/final_plot.png)

### Evaluating Results
To gauge the accuracy of the clusters, I decided to use the size of each one due to the correlation between the size and the specificity. I decided that having most be about the same size (and hopefully accuracy) and one larger one as a catch-all would prove to be a good structure for the user to navigate. 
The final counts can be seen here:

![final count](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-2/images/final_count.PNG)

As for the content of the clusters, I choose to look at the most common words for each, while also making sure to scan the actual content as well. There were very specific clusters for prepared salads, ice cream, fish and nut butters. See some examples at the bottom of this documentation. A perfect example of why also looking at the content is important is 
cluster 4. The word count showed promising results for trail mix, which was reflected in many trail mix items being in the cluster, but when looking at the content, the top items are all onions.

Cluster 4 word count:
![cluster4](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-2/images/cluster4-wordcount.PNG)

Cluster 4 items:
![4 items](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-2/images/cluster4-items.PNG)

Another cluster that was slightly less successful was cluster 11. This one returned all Whole Foods items, so was specific in that way, but the foods themselves varied and were only clustered due to the Whole Foods labelling. This is extremely
evident in the word count for this cluster.
![cluster11](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-2/images/cluster11-wordcount.PNG)

### Successful Clusters

###### Cluster 3 - Fish
![3](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-2/images/cluster3-wordcount.PNG)

###### Cluster 5 - Non-frozen Dairy
![5](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-2/images/cluster5-wordcount.PNG)

###### Cluster 6 - Ice Cream
![6](https://github.com/amina-brown/machine-learning/blob/master/clustering/iteration-2/images/cluster6-wordcount.PNG)
