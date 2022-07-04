# Neural_Network_Charity_Analysis

# Overview

Using machine learning, neural networks and the provided dataset, I will create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup. The original dataset consisted of a CSV of over 34,000 organizations that received funding from Alphabet Soup. The columns in the dataset included:

* EIN and NAME — Identification columns
* APPLICATION_TYPE — Alphabet Soup application type
* AFFILIATION — Affiliated sector of industry
* CLASSIFICATION — Government organization classification
* USE_CASE — Use case for funding
* ORGANIZATION — Organization type
* STATUS — Active status
* INCOME_AMT — Income classification
* SPECIAL_CONSIDERATIONS — Special consideration for application
* ASK_AMT — Funding amount requested
* IS_SUCCESSFUL — Was the money used effectively

The goal was to attempt to develop a model with over 75% accuracy in predicting success from the given data.

# Results

### Data Preprocessing

The first step was to examine and preprocess the provided dataset.

* The target variable was the IS_SUCCESSFUL column.
* The unnecessary data for the purposes of this model were the EIN and NAME columns.
* All other columns were considered potential features for the model. The next steps were to bin, encode, and scale the   data.
* Any APPLICATION_TYPE with less than 1000 entries were binned into OTHER.
* Any CLASSIFICATION with less than 1000 entries were binned into OTHER.
* All "object" type columns were encoded using OneHotEncoder.
* The SPECIAL_CONSIDERATIONS_N column was dropped, as it was redundant to the SPECIAL_CONSIDERATIONS_Y column.
* All columns were then scaled using StandardScaler.

### Compiling, Training, and Evaluating the Model

In the initial model I used:

* two layers -- one with 80 neurons, the second with 45 neurons -- providing me with 6,891 total and trainable parameters;
* both layers used 'relu' activation functions;
* the output layer used 'sigmoid' activation function. Unfortunately I was only able to achieve 72.4% accuracy with this model.

I tried three more models in an attempt to reach 75% accuracy. In my subsequent attempts I attempted:

* binning INCOME_AMT values greater than $5 million into a '5M+' bin
* adding a third hidden layer
* increasing the total number of trainable parameters to as high as 7,591
* increasing training epochs from 100 to as high as 200
* trying out the 'adam', 'adamax' and 'nadam' optimizers when compiling the model;
* using 'tanh' activation functions on the hidden layers;
* un-binning certain values by lowering the threshold from 1000 values to 700 values on both APPLICATION_TYPE and CLASSIFICATION.

Across all four of my attempts I never managed to raise my models' accuracy above 74%.

# SUMMARY

With the aforementioned failed attempts in neaural networks to improve accuracy beyond 74%, my recommendation would be to attempt some other methods such as Random Forests or SVM to yield better results. In neural networks there are too many moving parts to be able to pinpoint which would make the most impactful improvment in accuracy. 
