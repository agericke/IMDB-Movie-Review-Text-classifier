# IMDB MOVIE REVIEW TEXT CLASSIFIER

This project builds a text classifier using a __Logistic Regression__ to determine whether a movie review is expressing positive or negative sentiment. The data come from the website IMDB.com.

This project reads movie reviews from the IMDB website, then compares several different approaches by cross-validting accuracies. Once the model is correctly tuned, it is tested its generalization capacity with a test set and finally we compute an anlysis on the errors.

We use sklearn python packge to classify movie reviews as positive or negative.

## Summary

We read IMDB moviie reviews data for classifying them as positiveor negative. For doing so, we vectorize the reviews and create a vocabulary from all the reviews. For tokenazing the reviews, we define severl different arguments tht can take different options:

- __keep_internal_punctuation__: Whether or not to keep internal punctuation of the reviews.
- __feture_funcs__: Feture functions to use in the vectorization.
- __min_freqs__: List of posible min_frequencies values to use in order to include a word in the vocbulary.

We computed an analysis of all the possible vlues for the arguments and obtained tht the best model was set with features:

`'punct': True, 'features': (token_pair_features lexicon_features ), min_freq': 2`

This model obtained a cross_validated accuracy of:
__`accuracy': 0.77`__

We also print an average of the accuracies obtained by each feature. We observed that the features with best accuracies were token_pair_features in combination with lexicon_features and the worst accuracies were obtained with lexicon_features enabled only.

We obtained test accuracy of:
__`accuracy': 0.7425`__

So we see that the model generalizes very good.

Then we perform an analysis on the top coeficients associated to each class. For the positive class, we obtain that the top 3 coefficieents are:
__Positive class top coefficients__:
- pos_words: 0.50491
- token_pair=it__is: 0.25105
- token_pair=i__think: 0.22698

__Negative class top coefficients__:
- neg_words: -0.66914
- token_pair=the__worst: -0.36263
- token_pair=is__so: -0.29486

Finally, we perform an additional analysis to increase even more our model accuracy by providing additional features to the model and answer possible conflictive questions as you can see in the document ShortAnswer.txt.

You can also play with the interactive notebook provided in the repository to test all the dfferent functions and understand their objective and results.

