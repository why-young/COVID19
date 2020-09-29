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
