# restaurant_revenue_prediction
Predict annual restaurant sales based on objective measurements (kaggle)  <br />
A link to competition - https://www.kaggle.com/competitions/restaurant-revenue-prediction/submissions
It's a regression problem. This data set has only 137 samples and 41 features. Most of the features have no description so we can't say anything about them. <br />
My notebooks description: 

1. catboost preproc.ipynb <br />
I chose the catboost model because it can work with categorical variables without any preprocessing and I used Optuna for hyperparameters tuning. I wanted to use LeaveOneOut, but with Optuna it could be to slow, so after the best hyperparameters were found I used RandomSearch with a small grid to clarify hyperparams and fitted the model. Finally, my score was 1809288 and the best score on Kaggle is 1727811, which is quite close. <br />
P.S. I think that the open part of data is very small so the model has a poor ability to generalize and the score can change dramatically with another split. 

2. KNN_reg.ipynb <br />
Features without description look like numerical features after discretization and I wanted to work with them as they are all categorical. I fitted KNN regression model with Hamming distance. and used Sequential Feature Selector for feature selection. The best score: 1963726

3. Categorical_features_encoding.ipynb <br />
This is a study notebook where I used different methods of categorical encoding :) 
- Ordered Integer encoding
- Mean Encoding
