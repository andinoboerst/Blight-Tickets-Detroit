# Blight-Tickets-Detroit
## Classification Problem for Blight Tickets in Detroit


This project was completed as part of the \"[Applied Machine Learning in Python](https://www.coursera.org/learn/python-machine-learning)\" course by the University of Michigan on Coursera.

The dataset (in the .zip file) uploaded with this file was provided during the course and is based on a Kaggle competition (which includes the datasets) found here: [https://www.kaggle.com/competitions/detroit-blight-ticket-compliance/data](https://www.kaggle.com/competitions/detroit-blight-ticket-compliance/data).

To finish this project the notebook goes through the whole process of:
* Processing and cleaning the data
* Preparing the data for classification
* Training the classification model with GridSearch for hyperparameter tuning
* Predicting the test data

The packages used in this notebook include pandas for data processing and sklearn for the Gradient Boosting Classifier and the GridSearch package.

### Problem Description

This dataset is about blight tickets issued in the Detroit area, showing the compliance to paying these tickets. The goal is to develop a classification model that returns the probability for future cases to be compliant. The cases to be returned are provided in the 'test.csv' file and the training data is provided in the 'train.csv' file. Additionally there are two more .csv files containing information about addresses and their latitude and longitudonal coordinates.



The class is set to either (0 for not compliant), (1 for compliant) or (NaN for not responsible) in the \"compliance\" feature of the train data set.

All of the features in the train and test datasets are shown below.


  readonly/train.csv - the training set (all tickets issued 2004-2011)
  
  readonly/test.csv - the test set (all tickets issued 2012-2016)
  
  readonly/addresses.csv & readonly/latlons.csv - mapping from ticket id to addresses, and from addresses to lat/lon coordinates.
  
  Note: misspelled addresses may be incorrectly geolocated.
  
  **Data fields**
  
  train.csv & test.csv
  
  * ticket_id - unique identifier for tickets
  * agency_name - Agency that issued the ticket
  * inspector_name - Name of inspector that issued the ticket
  * violator_name - Name of the person/organization that the ticket was issued to
  * violation_street_number, violation_street_name, violation_zip_code - Address where the violation occurred
  * mailing_address_str_number, mailing_address_str_name, city, state, zip_code, non_us_str_code, country - Mailing address of the violator
  * ticket_issued_date - Date and time the ticket was issued
  * hearing_date - Date and time the violator's hearing was scheduled
  * violation_code, violation_description - Type of violation
  * disposition - Judgment and judgement type
  * fine_amount - Violation fine amount, excluding fees
  * admin_fee - $20 fee assigned to responsible judgments
  * state_fee - $10 fee assigned to responsible judgments
  * late_fee - 10% fee assigned to responsible judgments
  * discount_amount - discount applied, if any
  * clean_up_cost - DPW clean-up or graffiti removal cost
  * judgment_amount - Sum of all fines and fees
  * grafitti_status - Flag for graffiti violations
  
  train.csv only
  
  * payment_amount - Amount paid, if any
  * payment_date - Date payment was made, if it was received
  * payment_status - Current payment status as of Feb 1 2017
  * balance_due - Fines and fees still owed
  * collection_status - Flag for payments in collection
  * compliance [target variable for prediction] - (Null = Not responsible, 0 = Responsible, non-compliant, 1 = Responsible, compliant)
  * compliance_detail - More information on why each ticket was marked compliant or non-compliant
  
  
  The final grade can be seen in the picture below, with a ROC_AUC of 0.799:
  
  ![Ass4_grade](https://user-images.githubusercontent.com/73847250/185580524-509f4a09-a4df-4fe7-a794-b9efafecf360.png)

