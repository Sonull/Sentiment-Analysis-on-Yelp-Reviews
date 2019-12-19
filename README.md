# Sentiment-Analysis-on-Yelp-Reviews
Building a text classifier using Logistic Regression model and predicting the rating on Yelp

# Inspiration
A negative review, especially from an elite user can result in lost opportunity for a business. Businesses usually respond to negative reviews after a certain time but by then the damage is already done. This problem can be solved by performing real time prediction of rating while customer is typing the review so that action can be undertaken even before the review is live! This will significantly improve customer service and reduce the risk of losing customers.

# Methodology
# Feature Representation
* We used the column ‘reviews’ as the main source of features.
* One set of features were created without removing stop words or performing stemming
on them while another set of features was considered after performing these methods.
The idea was to assess the impact on the models.
* Moreover, feature engineering was done separately using the following N gram
sequences:
  * Unigram – taking one single word at a time
  * Unigram and Bigram – taking pairs of neighboring words along with each word individually Feature Weighting
* The following three kinds of feature weighting were tried:
  * Binary - if a word is present in the document, the weight is ‘1’ else ‘0’
  * Count - weights equal to number of occurrences of a word
  * TFIDF – Term Frequency (TF) Term frequency measures the local importance of the word by taking into account the number of times it appears in a document. Inverse Document Frequency (IDF) takes into account whether the word appears in other documents or not. For a word to be considered a signature word of a document, it shouldn’t appear that often in the other documents. The TF-IDF is the product of these two frequencies. For a word to have high TF-IDF in a document, it must appear a lot of times in said document and must be absent in the other documents.

# Logistic Regression Model
A 5% sample (~200K records) was selected from the population using Simple Random Sampling without Replacement. The data was divided into 75% Training data and 25% Testing data. A logistic regression model was then built using these features as the independent variables. The dependent variable that we were trying to predict was the column ‘rating’ which takes the values 1 through 5 on yelp. And thus, this was a multi-classification exercise.

Overall 12 Logistic regression models were built, and the corresponding results were analyzed. (Exhibit 8)
![pic3](https://github.com/Sonull/Sentiment-Analysis-on-Yelp-Reviews/blob/master/Pictures/pic3.png)


# Evaluation
Once the model was built on training data, we used it to predict ratings on testing data. In order to evaluate the performance, we calculated the accuracy in two methods:
1. Top 1 prediction defined as
![pic1](https://github.com/Sonull/Sentiment-Analysis-on-Yelp-Reviews/blob/master/Pictures/pic1.png)
2. Top 2 predictions defined as
![pic2](https://github.com/Sonull/Sentiment-Analysis-on-Yelp-Reviews/blob/master/Pictures/pic2.png)

#Validation on new text
In addition to predicting ratings using these models on the testing data, we also tested them on new texts to compare the predicted ratings. The following were the results obtained from thethree models which were built after removal of stop words and performing stemming and using features in unigram sequence

The model does not predict the correct rating in the first spot but makes the right prediction in the second spot. Interestingly, the top two predictions made by this model are in the opposite ends of the rating scale.


The model does not predict the correct rating in either of the two spots. Both the predictions are on the higher end of the rating scale while the text ideally belongs in the lower end.
![pic4](https://github.com/Sonull/Sentiment-Analysis-on-Yelp-Reviews/blob/master/Pictures/pic4.png)

The model predicts the correct rating in the first spot. Moreover, the prediction in the second spot also makes logical sense. 
![pic5](https://github.com/Sonull/Sentiment-Analysis-on-Yelp-Reviews/blob/master/Pictures/pic5.png)

# Source of data
https://www.yelp.com/dataset
