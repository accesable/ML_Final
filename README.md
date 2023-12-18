# Machine Learning Final Project

[Dataset Resource Link : Multi-Class Prediction of Cirrhosis Outcomes](https://www.kaggle.com/competitions/playground-series-s3e26/data?select=train.csv)

## Data Preprocessing

### Data class Value Range
```js
{
 'id': [0, 7904],
 'N_Days': [41, 4795],
 'Drug': ['D-penicillamine', 'Placebo'],
 'Age': [9598, 28650],
 'Sex': ['M', 'F'],
 'Ascites': ['N', 'Y'],
 'Hepatomegaly': ['N', 'Y'],
 'Spiders': ['N', 'Y'],
 'Edema': ['N', 'Y', 'S'],
 'Bilirubin': [0.3, 28.0],
 'Cholesterol': [120, 1775],
 'Albumin': [1.96, 4.64],
 'Copper': [4, 588],
 'Alk_Phos': [289.0, 13862.4],
 'SGOT': [26.35, 457.25],
 'Tryglicerides': [33, 598],
 'Platelets': [62, 563],
 'Prothrombin': [9.0, 18.0],
 'Stage': [1, 4],
 'Status': ['D', 'C', 'CL']
 }
```
> `Status` is the categorical target with values `'C'` (censored), `'CL'` (alive due to liver transplant), and `'D'` (deceased), the goal appears to be to predict the outcomes of cirrhosis in patients. This is a multi-class classification problem, with the target variable being the status of the patient at a given number of days (`N_Days`).
> the test dataset; your objective is to predict the probability of each of the three `Status` values, e.g., `Status_C`, `Status_CL`, `Status_D`.