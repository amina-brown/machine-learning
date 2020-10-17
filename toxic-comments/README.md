# First Discussion
The task was to make edits to the features used in the starter code and compare the results of the different models (the best way to do this was to compare the ROC plots).

I choose to eliminate the period count and word count and replace them with a count of exclamation points, count of the word "hell", and count of upper case letters. This resulted in a minimally better result than the original.
Some issues I ran into when implementing the new features were that in attempting to make the "hell" count case insensitive, I received a variety of errors. I also think that in the future, it would help to expand the upper case count to be a ratio of sentences to uppercase letters to account for long comments that are only using upper cases at the beginning of sentences, but are stilll receiving a high count.
