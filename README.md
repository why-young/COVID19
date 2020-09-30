COVID19 Healthcare Data Analysis portfolio


1. Introduction

Recent pandemic due to COVID19 from China has impacted various aspects of our life. Although some patients do not show any sympotoms of the virus, other patients show severe symptoms that requires to be hospitalized. Due to the limited space of bed in hospitals, it is crucial to predict the length of the stay of patients.

The purpose of this project is to predict the length of stay based on features about hospitals and patient status.

The dataset was obtained from Kaggle competition (https://www.kaggle.com/nehaprabhavalkar/av-healthcare-analytics-ii).
Below shows the list of features:

Features about hospital
- case_id: case id of each patient
- Hospital_code: Unique code of each hospital
- Hospital_type_code: Unique code of hospital type
- City_Code_Hospital: City code of hospital
- Hospital_region_code: Region code of hospital
- Available Extra Rooms in Hospital: The number of extra rooms available in hospital
- Department: Department in which the case is taken care of
- Ward_Type: Unique code of each ward type
- Ward_Facility_Code: Unique code of each ward facility
- Bed Grade: Grade of bed in the ward

Featrues about patients
- patientid: id of each patient
- City_code_Patient: City code of each patient
- Type of Admission: Type of patient admission in the hospital
- Severity of Illness: Extent of illness when patients are admitted
- Visitors with Patients: The number of visitors who came with patients
- Age: Age of patients
- Admission_Deposit: Amount of admission deposit

Target:
- Stay: The number of days that each patient stays at hospital

2. Data Preprocessing

In order to perform Exploratory Data Analyses, I first made sure to check with NaN and convert "age" and "stay" into numerical variable for meaningful EDA.
I replaced all NaN in "Bed Grad" and "City_Code_Patient" to 0.

3. Exploratory Data Analyses

The purpose of the exploratory data analyses was to 
- identify relationship between each feature and target
- identify correlation between features
- identify unbalanced data by looking at distribution
- gain basic insights for important features to include

Before the analyses, I initially hypothesized that age and severity of illness will be the features with the most predictive power
and the number of visitors with the patients will be irrelevant with the length of stay.

Main conclusions of the Exploraty Data Analyses were:
- On the contrary to my hypothesis, the number of visitors with the patients showed strong pattern with the length of stay. As the number of visitors with the patients increased, patients tended stay longer
- Age was weakly related with the length of stay. Older people tended to stay longer in the hospital, but there was a lot of variation.
- As predicted, patients who showed more sevierity of illness tended to stay longer.

![alt text](https://github.com/why-young/COVID19/blob/master/num_visitors.png)

4. Developing model

Gradient boosting classification model was used. To select the best hyperparameters for n_estimators, learning_rate and max_depth,
I ran hyperparameter tuning with GridSearchCV that used Stratified 5-fold Cross validation.
First hyperparameter tuning was aimed at choosing best n_estimators and learning_rate, which was 0.1 and 1500, respectively.
Second hyperparameter tuning was aimed at choosing the best max_depth, which was 3.
With the best hyperparameters, model was fitted.
Feature importance plot was generated based on the final model, which showed the number of visitors with patients was the dominating importance over any other features.

5. Deploy solution

Predicted numeric values for the target(Stay) was again converted into string, which was the original data type.
I stored predicted values into the submission file.

