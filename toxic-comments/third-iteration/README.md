# Third iteration
The second iteration had strong results with SVC, so this iteration uses Ridge Regression in order to try something new. 

I chose ridge regression because it seemed like those who were performing the best had found success using it. In disussion 2, we had worked through adjusting the alpha value. I chose to 
leave it as the default based on my results from the previous investigation.

From there, I implemented a few things that I had been using in the other assignments. 
First, I added an ngrams parameter to the HashingVectorizer feature set. This was something I came across in working through creating the feature set for assignment 3.
Next, I changed the seed from 22 to over 150000, this was something that I had tried for assignment 2 and had yielded favorable results.

Overall, the training set performed really well, while the test set was slightly worse than before (still 92% accuracy), though that isn't necessarily an indication of how well the set will perform on the actual test set.
