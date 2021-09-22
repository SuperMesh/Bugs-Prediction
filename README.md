# Bugs-Prediction
  - [Problem Overview](#problem-overview)
  - [Dataset Descrption](#dataset-descrption)
  - [Exploratory Data Analysis](#exploratory-data-analysis)
  - [Data Cleaning and Preprocessing](#data-cleaning-and-preprocessing)
  - [Words Vectorization](#words-vectorization)
  - [Training and Evaluation](#training-and-evaluation)
  - [Conclusion](#conclusion)
  - [References](#references)


### Problem Overview

Given Github's issues with text and body, train a model that can predict bugs, features and questions. 

![](Snapshots/Bugs%20pred.png)

### Dataset Descrption

Dataset used here is from a hackathon hosted by [MachineHack](https://www.machinehack.com/). Go to the hackathon [homepage]((https://www.machinehack.com/hackathons/5e8327d352c028cd80a0bd99)) to know more about the dataset.

* Size of training set: 150,000 data points + 300,000 data points extra training data | Size of test set: 30,000 datapoints 
  
**Dataset Attributes** 
  - Title - the title of the GitHub bug, feature, question
  - Body - the body of the GitHub bug, feature, question
  - Label - Represents various classes of Labels - Bug - 0, Feature - 1, Question - 2

### Exploratory Data Analysis
  
The distribution of class labelled question is imbalanced. Hence, the extra dataset is used only for the under representated class. 

The text data is composed of different laguages. Hence only English text data was used for preprocessing and modelling.

![](Snapshots/Data%20dist1.png)

### Data Cleaning and Preprocessing

* **Steps**
  - Cleaning URLs and tags
  - Decontracting abbreviations
  - Cleaning emojis and special charcters
  - Removing stop words
  - Removing very long words
  - Lemmatizing words
  - Removing noisy alphabets and whitespaces

### Words Vectorization
 
 - Used bag-of-words since it is simple to understand and implement and performs well in text classification tasks.

![](Snapshots/50%20bug.png)

![](Snapshots/50%20feature.png)

![](Snapshots/50%20question.png)

 - GloVe (Global Vectors) learns vectors or words from their co-occurrence information, i.e. how frequently they appear together in large text corpus. It is a count based model as against word2vec which is a predictive model that uses feed-forward neural network that learns vectors to improve the predictive ability.

### Training and Evaluation

**Models**
  - Logistic Regression using SGD
  - Naive Bayes Classifier
  - Light Gradient Boosting Machine (LGBM)

**Logistic Regression on BOW vectors**

![](Snapshots/BOW%20Log.png)

**Naive Bayes on BOW vectors**

![](Snapshots/BOW%20NB.png)

**LightGBM on BOW vectors**

![](Snapshots/BOW%20Lgbm.png)

**Logistic Regression on Glove vectors**

![](Snapshots/Glove%20log.png)

**Logistic Regression on Glove vectors**

![](Snapshots/Glove%20lgbm.png)

**Results**

![](Snapshots/Test%20Table.png)

### Conclusion

The models built on BoW vectors performed much better than compared to GloVe vectors. It is also neccessary to check performance on TFIDF vectors and TFIDF weighted embedded vectors. As expected training time required for LightGBM was very high compared to Logistic Regression and Naive Bayes with marginal improvements in performance. 

**More models**

Training on LSTM and BERT transformer.  

### References
  - https://www.kaggle.com/gauravharamkar/github-static-semantic-word-embeddings
  
  Thanks to the above kernel which helped clear tons of doubts on cleaning tasks.


