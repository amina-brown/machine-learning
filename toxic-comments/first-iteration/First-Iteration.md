# First Iteration
For this iteration I choose the Linear SVM model. I choose this one because due to the nture of toxic comments, 
I thought it was important to not only choose a model with high accuracy, but one that also had the lowest amount of false negatives.

For this iteration, the only changes I made were to the feature set. Here, I made two types of changes. 
The first was to increase the number of features in the HashingVectorizer from 2**17 to 2**20.
The second change was to switch the added features from punc_count and word_count to ep_count (exclamation point count), hell_count (count of lowercase and upper "hell"), and
upper_ratio. upper_ratio was initially intended to be a ratio of uppercase letters to sentences, which would have identified non-standard uses of upper case letters. 
Instead, I changed it to identify and count the upper case letters that did not have a space before them. This would then indicate that more than just the first letter was upper case 
and likely is part of a string of uppercase letters.
