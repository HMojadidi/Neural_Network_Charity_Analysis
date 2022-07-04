# Neural_Network_Charity_Analysis

# Overview

Using machine learning, neural networks and the provided dataset, I will create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup. The original dataset consisted of a CSV of over 34,000 organizations that received funding from Alphabet Soup. The columns in the dataset included:

EIN and NAME — Identification columns
APPLICATION_TYPE — Alphabet Soup application type
AFFILIATION — Affiliated sector of industry
CLASSIFICATION — Government organization classification
USE_CASE — Use case for funding
ORGANIZATION — Organization type
STATUS — Active status
INCOME_AMT — Income classification
SPECIAL_CONSIDERATIONS — Special consideration for application
ASK_AMT — Funding amount requested
IS_SUCCESSFUL — Was the money used effectively

The goal was to attempt to develop a model with over 75% accuracy in predicting success from the given data.

# Results

Preprocessing

The first step was to examine and preprocess the provided dataset.

* The target variable was the IS_SUCCESSFUL column.
* The unnecessary data for the purposes of this model were the EIN and NAME columns.
* All other columns were considered potential features for the model. The next steps were to bin, encode, and scale the   data.
* Any APPLICATION_TYPE with less than 1000 entries were binned into OTHER.
* Any CLASSIFICATION with less than 1000 entries were binned into OTHER.
* All "object" type columns were encoded using OneHotEncoder.
* The SPECIAL_CONSIDERATIONS_N column was dropped, as it was redundant to the SPECIAL_CONSIDERATIONS_Y column.
* All columns were then scaled using StandardScaler.
