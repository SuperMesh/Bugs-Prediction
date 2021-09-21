# Bugs-Prediction
  - [Problem Overview](#problem-overview)
  - [Dataset Descrption](#dataset-descrption)


### Problem Overview

Given Github's issues with text and body, train a model that can predict bugs, features and questions. 

### Dataset Descrption

Dataset used here is from a hackathon hosted by [MachineHack](https://www.machinehack.com/). Go to the hackathon [homepage]((https://www.machinehack.com/hackathons/5e8327d352c028cd80a0bd99)) to know more about the dataset. The dataset set contains features like Location, Manufacture details, car features such as Fuel type, Engine, and usage parameters. Below is the app in Working condition.

* Size of training set: 150,000 data points + 300,000 data points extra training data | Size of test set: 30,000 datapoints 
  
* **Dataset Attributes**: 
  - Title - the title of the GitHub bug, feature, question
  - Body - the body of the GitHub bug, feature, question
  - Label - Represents various classes of Labels - Bug - 0, Feature - 1, Question - 2

### Exploratory Data Analysis
  
The distribution of class labelled question is imbalanced. Hence, the extra dataset is used only for the under representated class. 

The text data is composed of different laguages. Hence only English text data was used for preprocessing and modelling.
