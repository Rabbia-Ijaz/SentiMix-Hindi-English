# SentiMix-Hindi-English
Sentiment analysis on Hindi-English tweets dataset (Kaggle Competition SentiMix-Hindi-English)

## The whole process involved certain steps:
### File Reading
    In total, 3 files have been used
    train_conll.txt is used for training purposes, and it contains ids, sentences, sentiment. 
    Hindi_test_unalbelled_conll_updated.txt is used for testing, this file contains only ids and sentences. 
    test_labels_hinglish.txt is used to check the accuracy of testing, this file contains labels and ids.

### Preprocessing and Cleaning
    Preprocessing involved reading of files in proper format and storing them. In text files, sentences are broken into words and each word has a language label. We cannot use it exactly so we read the files and store the sentences in proper lists so that we can clean those sentences later.
    For Cleaning, we have written 4 cleaning functions
    RemoveEngStopWords(Sentences)removes English stop words such as articles and all extra words that have no sentiment.
    RemoveEmoji(Sentences)removes emojis from the tweets because we cannot use it for sentiment analysis because nowadays emojis are not used in a way it is meant for.
    RemoveChar(Sentences)removes all extra characters such as extra whitespaces, special characters, http links etc.
    RemoveNumbers(Sentences)removes all numbers from words because they cannot express sentiments

### Vectorization
    Vectorization is a process of converting text data into numbers. Machine Learning Algorithms cannot work on alphabets so we have to convert it into numbers. Two types of Vectorizer are used 
    CountVectorizer(max_features=10000, min_df=6, max_df=0.1)
    TfidfVectorizer()

### Model Implementation
    We implemented 4 different models and they were run on different vectorizers.
    RandomForestClassifier() was run on CountVectorizer data.
    SGDClassifier()was run on both CountVectorizer and TfidfVectorizer data. 
    LinearSVC()was run on both CountVectorizer and TfidfVectorizer data.
    MultinomialNB()was run on both CountVectorizer and TfidfVectorizer data.
 
### File Writing
    The Last step was to write the result in answer.txt file and zip it into answer.zip file.
    The format of answer.tx is:
    Uid,Sentiment
    1,positive
    2,negative

    The file should not have any extra line at the end.
    
### Results
    We implemented 4 different models
    RandomForestClassifier()
    CountVectorizer accuracy 66.27%

    SGDClassifier()
    CountVectorizer accuracy 61.90%
    TfidfVectorizer accuracy 65.53%

    LinearSVC()
    CountVectorizer accuracy 59.53%
    TfidfVectorizer accuracy 63.83%

    MultinomialNB()
    CountVectorizer accuracy 65.33%
    TfidfVectorizer accuracy 65.50%

