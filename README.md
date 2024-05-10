# SMS Spam Classifier

## Description
This project provides a simple web interface for classifying SMS messages as spam or not spam. It utilizes a machine learning model built with Scikit-Learn and a web interface created using Gradio. This project demonstrates the use of text classification techniques and how they can be applied to practical problems.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Code Snippets](#code-snippets)
- [Acknowledgments](#acknowledgments)

## Installation

To run this project, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/sir-hobbyjog/sms_spam_detector.git
   cd sms_spam_detector```

2. Download the dataset SMSSpamCollection.csv and place it in a folder named Resources within the project directory.  

## Usage
To run the application, execute the following command:  
```python sms_classifier.py```

Once the application is running, navigate to the provided local URL (usually http://127.0.0.1:7860/) in your web browser to interact with the model.  

## Code Snippets

### SMS Classification Function
Here is how the SMS classification model is set up:
```from sklearn.pipeline import Pipeline
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.svm import LinearSVC

def sms_classification(sms_text_df):
    text_clf = Pipeline([
        ('tfidf', TfidfVectorizer()),
        ('clf', LinearSVC())
    ])
    # Train the model
    text_clf.fit(features_train, target_train)
    return text_clf
```

###Predicting with the Model  
Using the trained model to predict whether a message is spam:
```
def sms_prediction(text):
    prediction = text_clf.predict([text])
    return 'The text message: "{}", is not spam.'.format(text) if prediction == 'ham' else 'The text message: "{}", is spam.'.format(text)
```

##Acknowledgments
Thanks to EdX for the dataset and starter code.
