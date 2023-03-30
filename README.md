# credit-risk-classification
## Credit RIsk Analysis 

## Overview on the purpose of this analysis

The purpose of the current modeling exercise is to build a model that can identify the creditworthiness of borrowers i.e. whether the risk of lending to a particular borrower is high or low. Higher the risk, lower is the credit worthiness for the bank and higher the risk of default which can lead to losses for the bank due to non recovery. Hence, its of utmost importance to identify loans with high risk with a label of high risk (=1 in our model). 

-- the data provided includes the size of the loan, rate of interest, income level of the borrower, debt to income ratio, the number of accounts that the borrower has with the bank, any derogatory marks on the account, total debt of the borrower as well as loan status. 

-- loan status is the actual key result that indicates credit risk and can be used as the y or target variable for the model

-- rest of the data points can be used as the features of the X variable

-- first data is split into training and testing samples for comparing final accuracy 

-- initally, this data is used as is and fit  into a logistic regression  model to predict low risk or high risk

### Commentary on the Accuracy, precision, and recall scores of the machine learning model 1

-- Prima facie, the accuracy score of the model looks good with 99.18% accuracy.

-- However, a confusion matrix and classification report gives more insight and shows that even though the precision and recall for low risk (0) is good (true negative and false negative), the precision and recall for high risk is 85% and 91% respectively, and leaving one desiring for better results so that high risk loans are not missed and accuratly flagged by the model.

### Commentary on the Accuracy, precision, and recall scores of the machine learning model 2

-- In an effort to improve the results, randomoversampler is used to reshape training data so that the data has labels have an equal number of data points so that the high risk data gets equal importance in terms of data being input

-- we see that the valuu count on y_resampled data yields equal number of 0 and 1 labels.

-- next we use the resampled data and fit and predict a logistic regression model another time hoping that results are better this time

-- accuracy score is a slight improvement at 99.38%, which is a positive outcome

-- confusion matrox comparison on two models show that lower false negatives are produced by new model

-- classification report shows that the recall score for high risk improves to 99% but precision is down to 84%. We consider this as a better outcome as the room for error in this model on predicting high risk loans is just 1%, that is 99% of times model predicts the high risk loans accurately, so this model is more suited for the bank to reduce probablity of losses. 

### Summary
The company can start using the second model as a pilot project and continue using traditional manual process of credit risk identification. 1% prediction error seems low, however, for a lending company, if the 1% of loans where predictions were wrong were for a loan of much bigger size than other loans, the losses will be significant. So the company can continue gathering more data and try to improve model and train the model for future use. 


