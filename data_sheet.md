# Datasheet Template


## Motivation

- The original dataset was constructed to support the paper **Structure‑based design
and classifcations of small
molecules regulating the circadian
rhythm period** published in nature.
- The final dataset with 4 features was constructed for the capstone project of a machine learning course. It did not have any input from subject matter experts and its only purpose is to support the model code in this repo.


 
## Composition

The dataset includes 171 molecules designed for functional domains of a core clock protein, CRY1, responsible for regulating circadian rhythm.

56 of the molecules are toxic and the rest are non-toxic which results in a imbalanced dataset with a bias towards non-toxic molecules.

## Collection process

- The original data was constructed from the results of physical experimentation.
- the final dataset is simply the same data but with only the "top" 4 features retained after a feature importance exercise.
    - the algorithm used was my design and was simply me playing with ideas in a very short time-frame
    - I do not especially trust the results and I would not use this dataset to make any "real" decisions ~ **_you shouldn't either!_**

## Preprocessing/cleaning/labelling

The original data had no missing values and did not have any cleaning methods applied
 
## Uses

The data in this repository is only to be used to support the code in the notebooks in this repository

## Distribution

- The original dataset is freely available from https://archive.ics.uci.edu/dataset/728/toxicity-2
    - License
        -  This dataset is licensed under a Creative Commons Attribution 4.0 International (CC BY 4.0) license.
        - This allows for the sharing and adaptation of the datasets for any purpose, provided that the appropriate credit is given.
    - citation: Gul, S., Rahim, F., Isin, S. et al. Structure-based design and classifications of small molecules regulating the circadian rhythm period. Sci Rep 11, 18510 (2021).
https://doi.org/10.1038/s41598-021-97962-5

- the final dataset is only available in this repo
    - do not use it for any real work
    - there is no license (I don't care what happens to it)

## Maintenance

Neither the original or the reduced dataset is actively maintained. it is provided as is.

