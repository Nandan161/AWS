# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Nandan Choudhary

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?

Initially, when submitting predictions, negative values were present in the predicted count column. Since Kaggle requires all predictions to be non-negative, the solution involved setting all negative values to zero before submission.


### What was the top ranked model that performed?

The best model after hyperparameter tuning achieved a Kaggle public score of 0.47108, which came from the second hyperparameter tuning attempt (submission_new_hpo2.csv).
The initial model had a score of 1.81999, and the score improved significantly after feature engineering and hyperparameter tuning​.


## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?

The exploratory analysis examined features like season, weather, temp, and windspeed, identifying patterns in demand fluctuations.
Additional features were created by extracting hour from the datetime column​.

### How much better did your model preform after adding additional features and why do you think that is?

The model’s Kaggle public score improved from 1.81999 (initial submission) to 0.59867 after adding new features.
The performance gain likely occurred because feature engineering allowed the model to capture time-based demand patterns, such as rush hours and seasonal effects​.


## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?

After hyperparameter tuning, the best score achieved was 0.47108 (submission_new_hpo2.csv).
This improvement was due to optimizing hyperparameters for models like XGBoost, RandomForest, and CatBoost.

### If you were given more time with this dataset, where do you think you would spend more time?

Further improvements could be made by:
    Exploring additional feature interactions (e.g., combining temp and humidity).
    Tuning more complex ensembles (stacking models).
    Using deep learning architectures like recurrent neural networks for time-series forecasting​

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.


| Model        | hpo1                  | hpo2                  | hpo3                  | Score  |
|-------------|-----------------------|-----------------------|-----------------------|--------|
| Initial     | Default parameters    | -                     | -                     | 1.81999 |
| Add Features | Feature extraction    | -                     | -                     | 0.59867 |
| HPO         | XGBoost tuning        | RandomForest tuning   | CatBoost tuning      | 0.47108 |
| HPO1        | CatBoost tuning       | XGBoost fine-tuning   | -                     | 0.48828 |
| HPO2        | XGBoost tuning        | RandomForest tuning   | Learning rate tuning  | 0.47108 |
| HPO3        | Feature engineering   | New loss function     | Ensemble tuning       | 1.57341 |



### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.
![alt text](model_train_score.png)
![alt text](model_test_score.png)
![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.
![alt text](model_train_score_all_hpo.png)
![model_test_score.png](img/model_test_score.png)

## Summary

The project successfully improved bike-sharing demand predictions through feature engineering and hyperparameter tuning.
The best Kaggle score improved from 1.81999 to 0.47108 through feature engineering and tuning.
Further improvements could come from stacked models, additional feature selection, and deep learning approaches.
