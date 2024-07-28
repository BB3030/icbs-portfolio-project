# Model Card



## Model Description

The selected model is a trainined ```scikit-learn``` Random Forest classifier that uses 4 features to predict whether a drug designed for functional domains of a core clock protein, CRY1, responsible for generating circadian rhythm is toxic or not.

### Inputs:

The model takes a single csv file as an input. The csv file requires these 4 features in the exact order ```[SpDiam_Dt, MDEC-23, SpMin3_Bhi, ATSC1v]```

### Outputs:

The output of the model is an array of flags where toxic==1 and non-toxic==0. There will be a flag for each row in the input csv.

e.g. a 1 in the 4th position in the output array indicates that the drug that corresponds to row 4 in the input csv is toxic

### Hyper-parameters:

The final model was fitted using the following hyper-parameters

```json
{
    'max_depth': None, 
    'max_features': 'sqrt', 
    'min_samples_leaf': 1, 
    'min_samples_split': 5, 
    'n_estimators': 100
}
```

---

## Performance

```
'Hold out' test set results
	Recall:		0.91 (correctly identified as toxic)
	Accuracy:	0.97
Full dataset results
	Recall:		0.95 (correctly identified as toxic)
	Accuracy:	0.98
```

The model has good recall which is the metric of importance in this case as it is a measure of how well the model correctly indentifies toxic drugs.

---

## Limitations

The model has only been trained on drugs designed for a particular purpose i.e.those  designed for _functional domains of a core clock protein, CRY1, responsible for generating circadian rhythm_

There was no training data pertaining to drugs designed for different purposes and we can not make the assumption this model will generalise to such drugs.

---

## Trade-offs

Because the number of drugs in the dataset is small, only 171, it was necessary to reduce the number of features in the original dataset significantly. 

There were far more features than drugs, 1203 vs 171, and any model fitted from such a dataset would always overfit and thus very unlikely to have any predictive power.

I chose to reduce the number of features to 4 as this seemed an appropriate size given the number of records. Tests on the hold-out dataset seem to indicate the model is seeming to generalise. But I am uncomfortable that I may have thrown away too much information. I find it hard to believe that the other 99.7% of features helf little preditive power.

If I had more time I would investigate other feature selection of engineering techniques like PCA.
