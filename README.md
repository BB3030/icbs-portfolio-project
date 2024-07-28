# Prediciting Viscosity in drugs that target core clock protein, CRY1, responsible for regulating circadian rhythm

The aim of this project is to try and find an accurate model that can be used to reliably predict whether a drug designed for functional domains of a core clock protein, CRY1, responsible for generating circadian rhythm is toxic or not.

Three commonly used classification models were trained, tuned and compared:
 - Random Forest
 - K Nearest Neighbours(KNN)
 - Logistic regression

 During the tuning of the models the performance metric ```recall``` was used as the primary performace evaluation metric instead of the more commonly used ```accuracy```.
 
 ```recall``` is a measure of the ability of the classifier to find all the toxic samples - possibly at the expense of mis-labelling non-toxic drugs as toxic. This was considered a reasonable trade off due to the importance of not miss-identifiying toxic drugs


---

## DATA
- The data used for training represent  has
    - 171 rows
        - 56 toxic
        - 115 non-toxic
    - 5 columns
        - 4 features
        - 1 toxicity flag
        - The features were chosen from the 1203 in the original dataset by selecting only those that seemed the most mathematically important to the classification.
- The original dataset is freely available from https://archive.ics.uci.edu/dataset/728/toxicity-2
    - License:
        - This dataset is licensed under a Creative Commons Attribution 4.0 International (CC BY 4.0) license.
        - This allows for the sharing and adaptation of the datasets for any purpose, provided that the appropriate credit is given.
    - citation: Gul, S., Rahim, F., Isin, S. et al. Structure-based design and classifications of small molecules regulating the circadian rhythm period. Sci Rep 11, 18510 (2021).
https://doi.org/10.1038/s41598-021-97962-5

---

## MODEL 

The best performing classifier was a ```Random Forest``` model which had both good ```recall``` and ```accuracy```

---

## HYPERPARAMETER OPTIMSATION

The final model was fitted using the following hyper-parameter values

```json
{
    'max_depth': None, 
    'max_features': 'sqrt', 
    'min_samples_leaf': 1, 
    'min_samples_split': 5, 
    'n_estimators': 100
}
```

These values were chosen by utilising:

- grid search with
- 5-fold cross-validation and
- scoring metric of _**recall**_

---

## RESULTS

```text
'Hold out' test set results
	Recall:		0.91 (correctly identified as toxic)
	Accuracy:	0.97
Full dataset results
	Recall:		0.95 (correctly identified as toxic)
	Accuracy:	0.98
```

The above results seem fairly impressive but it should be noted that results this good could be an indicator of over-fitting bearing in mind how small the training dataset is.

In a real project _(which this is not)_ an effort would be made to aquire more experimental data as well as seeking advice from subject matter experts during the feature reduction phase.


