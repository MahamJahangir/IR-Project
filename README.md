# Information Retrieval Project

We have been given six datasets and ask to select three out of them. Then we have to perform three different classification algorithms on them after getting datasets ready for processing by doing required pre-processing on them. Nature of each dataset is different.

# HOW TO RUN THIS PROJECT

Download the repository to your local computer using link: 
https://github.com/MahamJahangir/IR-Project
and then download the required datasets as well. Links for the datasets selected for this project are:
-	https://archive.ics.uci.edu/ml/datasets/DBWorld+e-mails
-	https://archive.ics.uci.edu/ml/datasets/Legal+Case+Reports
-	https://archive.ics.uci.edu/ml/datasets/Sentence+Classification

There are separate python file for each dataset in the repository.
- Algorithms on SENTENCE CORPUS DATA.ipynb
- Algorithms on SENTENCE dbworld.ipynb
- IR_LegalDataset_v1.ipynb

You can run them individually to see the result of our analysis on each dataset. 

# Reason for choosing the datasets
We have chosen three datasets for our project. These are:
- DBWorld Emails (TF Matrix Format)
- Sentence Classification (Text Format)
- Legal Case Reports (XML Format)

The reason for choosing these was that they were the only ones on which labelling was available and we can only run classification tasks such as kNN, Naive Bayes and Rocchhio on pre-labelled datasets. Other three datasets are clustering problems and it was not requirement of this project.

# ANALYSIS PERFORMED
Three types of classification tasks have been run on each dataset:
- Naive Bayes Classification
- kNN Classification
- Rocchhio Classification
The results have been presented in the form of accuracy.

# DATASET 1 
# DBWORLD EMAILS
https://archive.ics.uci.edu/ml/datasets/DBWorld+e-mails

## Dataset basics:
The data is in the .mat files. Separate file for subjects and bodies are there in the data. These have to be read separately with their labels and classification tasks applied to them separately.

##Working:
- The dataset is already preprocessed. Therefore there is no preprocessing to be done. 
- The dataset is then split into training and test sets using scikitlearn’s training_test_split.
- Each classification task is performed on the dataset and analyzed using accuracy.

- 3 built in SKlearn classifiers are used:
  - MultinomialNB (Naive Bayes)
  - NearestCentroid (Rocchio)
  - KNeighborsClassifier


# DATASET 2 
# SENTENCE CLASSIFICATION
https://archive.ics.uci.edu/ml/datasets/Sentence+Classification
## Dataset basics:
- Only labeled data is considered for processing

## Working:
- Files are read from training_set and test_set folders.
- Each file has multiple lines. Each line starts with the "label" and then "sentence" separated by "tab".
- after reading preprocessing is applied. 
  - stopwords removed
  - label and sentence separated
- Sentences are converted into vectors using Sklearn function "TfidfVectorizer()".
- Dataset is split into test and training data using scikitlearn’s training_test_split.

- 3 built in SKlearn classifiers are used:
  - MultinomialNB (Naive Bayes)
  - NearestCentroid (Rocchio)
  - KNeighborsClassifier

- Accuracy  is used as an evaluation measure  
  

# DATASET 3 
# LEGAL CASE REPORTS
https://archive.ics.uci.edu/ml/datasets/Legal+Case+Reports

## Dataset basics:
Dataset is in xml format however few tags are not written in the proper format.
There are three folders in the CORPUS
Citation_class
Citations_summ
Fulltext
We have used files from Citation_class folder. There are 2754 files in the folder.
<class> tag contains the label
<text> tag contains the data/text used for classification.

## Working:
- First of all files are read from “Citation_class” folder(2754 files).
- Each file is in XML format. Files are first read as text and correction is made in the “tag”. One example is _”id=_ is replaced by _id=”_. Python notebook contains more “tags” in wrong format.
- Once XML format is corrected than files are read using “LXML” library for XML processing.
Preprocessing is applied.
- label(<class>) and sentence<text> separated
- Sentences and labels are converted into vectors using Sklearn function "TfidfVectorizer()".
- Dataset is split into test and training data using scikitlearn’s training_test_split.

3 built in SKlearn classifiers are used:
- MultinomialNB (Naive Bayes)
- NearestCentroid (Rocchio)
- KNeighborsClassifier
