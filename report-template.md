# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Jatin Patel

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
TODO: The total count of negative values was determined. (predictions < 0).sum()
All the negative values were converted to 0. predictions[predictions<0] = 0
The predictions dataframe was assigned to the 'count' feature of submission.csv file.

### What was the top ranked model that performed?
TODO:, WeighterEnsemble_L3 model, happened to perform with the highest accuracy, in every training phase generating the score_val of -52.63186262808237
in the intial training phase, -31.085724533714913 after feature engineering and  after hyperparameter tuning.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
TODO: During the exploratory data analysis, two new features:
(1). 'temp_diff' using the existing features - 'temp' and 'atemp',
(2). An 'hour' feature, extracting the 'hour' data from the datetime feature,
were introduced.

### How much better did your model preform after adding additional features and why do you think that is?
TODO: (1). Initially, the Root Mean Square Logarithmic Error (RMSLE), or the Kaggle score happened to be 1.80851.
(2). In the net training cycle, new features viz. - 'hour', 'temp_diff', were added. This improved the RMSLE score to 0.75670.
(3). In the final training cycle, hyperparameter tuning was performed, and the resulting score happened to be 0.51982.

The above data depicts the improvement in performance of the best-performing model as a result, of Feature Engineering and Hyperparameter Tuning.
Therefore, Feature Engineering and Hyperparameter Tuning play a crucial role in the overall performance of the model.
Feature Engineering helps bring out several essential features that may be more realistic and important in deciding (predicting) the target under study.
Hyperparameter tuning defines the configuration of the algorithm for the training process. 


## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
TODO: The model-performance certainly improved after trying new hyperparameters, but would have become much better if several other hyperparameters,
or other available combinations, were experimented.

### If you were given more time with this dataset, where do you think you would spend more time?
TODO:If I were given more time, I would spend more time in EDA and hyperparameter tuning because it could really generate several important insights and
configurations for the model, which would help it achieve better results.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default_vals|default_vals|NN|1.78173|
|add_features|default_vals|default_vals|GBM|0.76319|
|hpo|default_vals|default_vals|num_bag_folds|0.52598|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: 

![model_train_score.png](/model_train_score.png)


### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: 

![model_test_score.png](/model_test_score.png)

## Summary
TODO: The project overall, introduced me to the importance of Feature Engineering, hyperparameter tuning, and the proper realization of the cost
metrics, to be able to generate a highly accurate model that performs well with the external data, that it wasn't trained on. 
(1). Feature Engineering aims at generating new features that may not originally be present in the dataset, from the previously existing ones. It also 
involves the removal of features that may not be important for the target.
(2). Hyperparameters define the configuration of the algorithm before the model training actually begins and proper hyperparameter tuning helps in increasing the overall accuracy of the model.

Proper Feature Engineering mechanisms followed by adequate hyperparameter tuning is the key to training a highly accurate model.

