#**Stock Sentiment Analysis using Random Forest and Bag of Words**
This project performs sentiment analysis on financial news headlines to predict stock market trends. Using the Bag of Words model and a Random Forest classifier, the system identifies whether public sentiment is positive or negative based on textual data from news sources.
##**Project Overview**
The dataset contains daily news headlines for specific dates, along with sentiment labels. The goal is to use past news data to predict the sentiment label of stock market news, which could be helpful for investors and analysts in decision-making.
##**Workflow**
1.Data Splitting
The dataset is split into training and testing data using a cutoff date (train = df[df['Date'] < '20150101'], test = df[df['Date'] > '20141231']).

2.Text Preprocessing
Removed all non-alphabetic characters from the headlines using regex.
Renamed columns to numerical indices (0 to 24) for ease of access.
Converted all headlines to lowercase.
Combined the 25 news headlines for each row into a single string for model training.

3.Feature Extraction
Implemented a Bag of Words model using CountVectorizer with bigrams (ngram_range=(2, 2)).
Transformed the text data into numeric vectors for both training and testing sets.

4.Model Building
Used a Random Forest Classifier with 200 estimators and 'entropy' as the criterion.
Trained the model on the processed training dataset.

5.Model Evaluation
Predictions were made on the test dataset.
Evaluated using confusion_matrix, accuracy_score, and classification_report.
##**Results**
Accuracy: 85.18%
              precision    recall  f1-score   support

           0       0.99      0.70      0.82       186
           1       0.78      0.99      0.87       192

    accuracy                           0.85       378
   macro avg       0.88      0.85      0.85       378
weighted avg       0.88      0.85      0.85       378


