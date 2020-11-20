# Second Iteration
For this iteration I choose the Linear SVC model with a C value of .01. I choose this one because due to the nature of toxic comments, 
I thought it was important to not only choose a model with high accuracy, but one that also had the lowest amount of false negatives.

For this iteration, the only changes I made were to the C value. The experimentation is documented in the discussion 3 thread on canvas, and also below: 

For this assignment, I choose to look at C values that were less than 1. Using 1 (the default) as the starting place, I choose to also compare .01, .001, .0001, and .00001. The initial linear_model.SGDClassifier() model and the default LinearSVC() were already performing quite well, so very small changes become more meaningful. For the training set, the ROC plot shows that .01 and .001 were stand out values, but since the ROC plot is looking at positives, it's important to also consider the negative values - particularly the false negatives. In that case, the .01 and .001 values were still better than the other non-defaults, but the default value also did quite well with 77 FN, which was better than the .001 value of 158, but not better than the .01 value of 54 false negatives.

For the test set, the results were quite similar where the values 1, .01, and .001 were stand outs. Here, the .001 model did somewhat better, but the differences between them were closer than in the training set. Again, looking at the false negatives, the .001 value was most favorable, with the .01 value close behind. Overall, I think the .01 value is the best option, and the SVC model, in general, is a solid choice for future iterations.

The link to the code for the different C values is [here](https://github.com/amina-brown/machine-learning/blob/master/toxic-comments/toxiccomments_discussion3.ipynb)
