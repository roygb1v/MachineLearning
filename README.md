# MachineLearning
Big Data Analysis Project

Here, I intend to use semi-supervised machine learning to gather insights into customer sentiments.

From an excel spreadsheet, there are two sheets : one tab is from Twitter, another is from Facebook.

Since the Twitter dataset already provides us with sentiments as labels (Positive, Negative and Neutral), I will use that.

Facebook only has Likes which is not so useful to me.

1. I will let the Feature set X take the Twitter column "Remarks" (i.e X = df["Remarks"]) and y take the Twitter Sentiment column (i.e y = df["Sentiment"].

2. I will next split, test and train the Twitter dataset using Scikit-Learn train_test_split. I will split 70-30 where 70% of the dataset is used to train the model.

3. I will fit the model (i.e model.fit(X_train, y_train)).

4. I will then use the 'trained' model to predict the splitted data. i.e y_pred = model.predict(X_test)

5. I will then evaluate my models accuracy using .score(y_test, y_predict).

6. The models I will use for classification are : K-Nearest Neighbors (I will use neighbors=5 as default) or Logistic Regression.

7. If the accuracy of my model is good, I will proceed to use the model to predict the unlabeled data from the Facebook dataset.

8. There are 1000 observations in Facebook dataset. To be safe, I will manually split the data into 5 chunks (200 obs each). In the first chunk of observation, I will manually label the data. Then I will use the model to predict the 200 'labeled' data. If there is not much difference in the score, I will proceed to use the model on all the observations.

9. My rationale is since the new data from Facebook becomes part of the data for which my model will be trained on, I want to ensure the data does not drastically affect my model's accuracy.

10. I will then output the predicted data on a new column (i.e df["Predicted"] = model.predict(X_test))

These workflow may be subjected to changes as I read more on NLP.
